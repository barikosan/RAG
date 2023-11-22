# SparkWikiRAG
SparkWikiRAG: Enhanced Question Answering with Spark NLP and Wikipedia

This project aims to answer questions from "Mental health" wikipedia page using Retrieval Augmented Generation (RAG) technique with Spark NLP models.

It consists of three main steps:
## Retrieval:
   * Relevant data was retrieved and processed from "Mental health" page of the knowledge base wikipedia using wikipedia api. (https://en.wikipedia.org/wiki/Mental_health)
   * 10 Questions were manually curated based on the information relevant to that page.
   * After data collection, data was split into sentences and sentence embeddings were generated using Spark NLP pipeline.

## Augmentation:
  * Embeddings were stored in ChromaDB vector database which uses advanced indexing techniques to enable fast and accurate search of high-dimensional vectors.
  * Queried ChromaBD to augment the question prompts with the contextually relevant information from the dataset.

## Generation:
  * Fed augmented prompts to several LLM-based Spark NLP QA models to generate answers.
  * In total, 2 medical (flan_t5, clinical_notes_QA) and 3 non-medical (albert,bert,roberta) QA models were used.
    

The architecture of the overall system is as follows:



![rag_architecture](https://github.com/barikosan/SparkWikiRAG/assets/23119100/b864204c-9f88-4a32-bb85-26f3f729600d)
