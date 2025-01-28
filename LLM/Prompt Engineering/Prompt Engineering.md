[提示工程指南 | Prompt Engineering Guide](https://www.promptingguide.ai/zh)

## 模型设置

**Temperature**：简单来说，`temperature` 的参数值越小，模型就会返回越确定的一个结果。如果调高该参数值，大语言模型可能会返回更随机的结果，也就是说这可能会带来更多样化或更具创造性的产出。

**Top_p**：同样，使用 `top_p`（与 `temperature` 一起称为核采样的技术），可以用来控制模型返回结果的真实性。如果你需要准确和事实的答案，就把参数值调低。如果你想要更多样化的答案，就把参数值调高一些。 一般建议是改变 Temperature 和 Top P 其中一个参数就行，不用两个都调整。

**Max Length**：您可以通过调整 `max length` 来控制大模型生成的 token 数。

**Stop Sequences**：`stop sequence` 是一个字符串，可以阻止模型生成 token

**Frequency Penalty**：`frequency penalty` 是对下一个生成的 token 进行惩罚，这个惩罚和 token 在响应和提示中出现的次数成比例， `frequency penalty` 越高，某个词再次出现的可能性就越小

**Presence Penalty**：`presence penalty` 也是对重复的 token 施加惩罚，但与 `frequency penalty` 不同的是，惩罚对于所有重复 token 都是相同的。出现两次的 token 和出现 10 次的 token 会受到相同的惩罚。


## 主题

- [文本概括](https://www.promptingguide.ai/zh/introduction/examples#%E6%96%87%E6%9C%AC%E6%A6%82%E6%8B%AC)
- [信息提取](https://www.promptingguide.ai/zh/introduction/examples#%E4%BF%A1%E6%81%AF%E6%8F%90%E5%8F%96)
- [问答](https://www.promptingguide.ai/zh/introduction/examples#%E9%97%AE%E7%AD%94)
- [文本分类](https://www.promptingguide.ai/zh/introduction/examples#%E6%96%87%E6%9C%AC%E5%88%86%E7%B1%BB)
- [对话](https://www.promptingguide.ai/zh/introduction/examples#%E5%AF%B9%E8%AF%9D)
- [代码生成](https://www.promptingguide.ai/zh/introduction/examples#%E4%BB%A3%E7%A0%81%E7%94%9F%E6%88%90)
- [推理](https://www.promptingguide.ai/zh/introduction/examples#%E6%8E%A8%E7%90%86)

## 通用技巧

包含要素：
- **指令**：想要模型执行的特定任务或指令。
- **上下文**：包含外部信息或额外的上下文信息，引导语言模型更好地响应。
- **输入数据**：用户输入的内容或问题。
- **输出指示**：指定输出的类型或格式。

使用指令：“写入”、“分类”、“总结”、“翻译”、“排序”

提示越具体和详细，结果就越好

避免说不要做什么，而是说要做什么

## 零样本提示 zero-shot prompt

_提示：_

```
将文本分类为中性、负面或正面。文本：我认为这次假期还可以。情感：
```

_输出：_
```
中性
```

## 少样本提示 few-shot

_Prompt:_

```
A "whatpu" is a small, furry animal native to Tanzania. An example of a sentence that uses the word whatpu is:We were traveling in Africa and we saw these very cute whatpus. To do a "farduddle" means to jump up and down really fast. An example of a sentence that uses the word farduddle is:
```

_Output:_

```
When we won the game, we all started to farduddle in celebration.
```

## 链式思考 Chain-of-Thought Prompting

如果这样提示无法给出正确答案：
_提示：_

```
这组数字中的奇数加起来是一个偶数：4、8、9、15、12、2、1。
A：答案是False。

这组数字中的奇数加起来是一个偶数：17、10、19、4、8、12、24。
A：答案是True。

这组数字中的奇数加起来是一个偶数：16、11、14、4、8、13、24。
A：答案是True。

这组数字中的奇数加起来是一个偶数：17、9、10、12、13、4、2。
A：答案是False。

这组数字中的奇数加起来是一个偶数：15、32、5、13、82、7、1。
A：
```

_输出：_（错误）

```
答案是True。
```

使用CoT提示：

_提示：_

```
这组数中的奇数加起来是偶数：4、8、9、15、12、2、1。
A：将所有奇数相加（9、15、1）得到25。答案为False。
这组数中的奇数加起来是偶数：17、10、19、4、8、12、24。
A：将所有奇数相加（17、19）得到36。答案为True。
这组数中的奇数加起来是偶数：16、11、14、4、8、13、24。
A：将所有奇数相加（11、13）得到24。答案为True。
这组数中的奇数加起来是偶数：17、9、10、12、13、4、2。
A：将所有奇数相加（17、9、13）得到39。答案为False。
这组数中的奇数加起来是偶数：15、32、5、13、82、7、1。
A：
```

_输出：_

```
将所有奇数相加（15、5、13、7、1）得到41。答案为False。
```

## Auto-CoT

- 阶段1：**问题聚类**：将给定问题划分为几个聚类
- 阶段2：**演示抽样**：从每组数组中选择一个具有代表性的问题，并使用带有简单启发式的 Zero-Shot-CoT 生成其推理链

![](Pasted%20image%2020240720132442.png)