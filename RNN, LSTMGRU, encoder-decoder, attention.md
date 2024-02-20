# RNN, LSTM/GRU, encoder-decoder, attention

## RNN

- 👉 RNN基本原理 [一文搞懂RNN（循环神经网络）基础篇 - 知乎](https://zhuanlan.zhihu.com/p/30844905)

- [一文看懂循环神经网络 RNN（2种优化算法+5个实际应用）](https://easyai.tech/ai-definition/rnn/)

  动画 [Illustrated Guide to Recurrent Neural Networks | by Michael Phi | Towards Data Science](https://towardsdatascience.com/illustrated-guide-to-recurrent-neural-networks-79e5eb8049c9)
  

Pytorch examples:

- [NLP From Scratch: Classifying Names with a Character-Level RNN — PyTorch Tutorials 2.1.0+cu121 documentation](https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html)

- [NLP From Scratch: Generating Names with a Character-Level RNN — PyTorch Tutorials 2.1.0+cu121 documentation](https://pytorch.org/tutorials/intermediate/char_rnn_generation_tutorial.html#creating-the-network)

  my example with lstm: https://github.com/Valkure-Yip/pytorch-generating-names-rnn
  One-to-many network generates name, sequence length of nn.LSTM = 1

- [NLP From Scratch: Translation with a Sequence to Sequence Network and Attention — PyTorch Tutorials 2.1.0+cu121 documentation](https://pytorch.org/tutorials/intermediate/seq2seq_translation_tutorial.html?highlight=seq2seq): translation, many to many with GRU

## LSTM & GRU

- 👉 动画 [Illustrated Guide to LSTM’s and GRU’s: A step by step explanation | by Michael Phi | Towards Data Science](https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21)
- [Understanding LSTM Networks -- colah's blog](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)

## encoder-decoder

- 👉 Encoder-decoder detailed explain & attention: [A Guide to the Encoder-Decoder Model and the Attention Mechanism | by Eduardo Muñoz | Better Programming](https://betterprogramming.pub/a-guide-on-the-encoder-decoder-model-and-the-attention-mechanism-401c836e2cdb)

- with pytorch code：[10.6. The Encoder–Decoder Architecture — Dive into Deep Learning 1.0.3 documentation](https://d2l.ai/chapter_recurrent-modern/encoder-decoder.html) 
  and [10.7. Sequence-to-Sequence Learning for Machine Translation — Dive into Deep Learning 1.0.3 documentation](https://d2l.ai/chapter_recurrent-modern/seq2seq.html)

- Video explain: [Encoder-decoder architecture: Overview - YouTube](https://www.youtube.com/watch?v=zbdong_h-x4&ab_channel=GoogleCloudTech)

- Hugging Face model: https://huggingface.co/docs/transformers/model_doc/encoder-decoder

## self-attention & transformer

- 👉 Detailed explain of self-attention & transformer with pytorch codes [Transformers from scratch | peterbloem.nl](https://peterbloem.nl/blog/transformers)
- Positional encoding: [A Gentle Introduction to Positional Encoding in Transformer Models, Part 1 - MachineLearningMastery.com](https://machinelearningmastery.com/a-gentle-introduction-to-positional-encoding-in-transformer-models-part-1/)
- A pytorch official example with code: [Language Modeling with nn.Transformer and torchtext — PyTorch Tutorials 2.0.1+cu117 documentation](https://pytorch.org/tutorials/beginner/transformer_tutorial.html#load-and-batch-data)
