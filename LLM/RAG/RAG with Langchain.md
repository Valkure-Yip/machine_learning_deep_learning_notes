[Build a Retrieval Augmented Generation (RAG) App | 🦜️🔗 LangChain](https://python.langchain.com/v0.2/docs/tutorials/rag/)
## RAG Pipeline
### 1. Indexing[​](https://python.langchain.com/v0.1/docs/use_cases/question_answering/quickstart/#indexing "Direct link to Indexing")

1. **Load**: First we need to load our data. We’ll use [DocumentLoaders](https://python.langchain.com/v0.1/docs/modules/data_connection/document_loaders/) for this.
2. **Split**: [Text splitters](https://python.langchain.com/v0.1/docs/modules/data_connection/document_transformers/) break large `Documents` into smaller chunks. This is useful both for indexing data and for passing it in to a model, since large chunks are harder to search over and won’t fit in a model’s finite context window.
3. **Store**: We need somewhere to store and index our splits, so that they can later be searched over. This is often done using a [VectorStore](https://python.langchain.com/v0.1/docs/modules/data_connection/vectorstores/) and [Embeddings](https://python.langchain.com/v0.1/docs/modules/data_connection/text_embedding/) model.
![](Pasted%20image%2020240803175259.png)
### 2. Retrieval and generation[​](https://python.langchain.com/v0.1/docs/use_cases/question_answering/quickstart/#retrieval-and-generation "Direct link to Retrieval and generation")

1. **Retrieve**: Given a user input, relevant splits are retrieved from storage using a [Retriever](https://python.langchain.com/v0.1/docs/modules/data_connection/retrievers/).
2. **Generate**: A [ChatModel](https://python.langchain.com/v0.1/docs/modules/model_io/chat/) / [LLM](https://python.langchain.com/v0.1/docs/modules/model_io/llms/) produces an answer using a prompt that includes the question and the retrieved data

![](Pasted%20image%2020240803175304.png)

## Conversational RAG

[Conversational RAG | 🦜️🔗 LangChain](https://python.langchain.com/v0.2/docs/tutorials/qa_chat_history/)

给retrieving过程加上对话历史：
原来是 query -> retriever
现在是  `(query, conversation history)` -> `LLM` -> `rephrased query` -> `retriever`