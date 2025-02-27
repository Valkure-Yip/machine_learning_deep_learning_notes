[High-Level Concepts - LlamaIndex](https://docs.llamaindex.ai/en/stable/getting_started/concepts/)

![](Pasted%20image%2020240722180127.png)

## Stages with RAG

![](Pasted%20image%2020240722180302.png)

- **Loading**: this refers to getting your data from where it lives -- whether it's text files, PDFs, another website, a database, or an API -- into your pipeline. [LlamaHub](https://llamahub.ai/) provides hundreds of connectors to choose from.
    
- **Indexing**: this means creating a data structure that allows for querying the data. For LLMs this nearly always means creating `vector embeddings`, numerical representations of the meaning of your data, as well as numerous other metadata strategies to make it easy to accurately find contextually relevant data.
    
- **Storing**: once your data is indexed you will almost always want to store your index, as well as other metadata, to avoid having to re-index it.
    
- **Querying**: for any given indexing strategy there are many ways you can utilize LLMs and LlamaIndex data structures to query, including sub-queries, multi-step queries and hybrid strategies.
    
- **Evaluation**: a critical step in any pipeline is checking how effective it is relative to other strategies, or when you make changes. Evaluation provides objective measures of how accurate, faithful and fast your responses to queries are.

