# 🧠 Biomedical Literature Q&A Chatbot using RAG

This repository contains a biomedical question-answering system based on Retrieval-Augmented Generation (RAG). The system integrates dense retrieval using MiniLM embeddings and FAISS with generative answering via a fine-tuned Mistral-7B-v0.3 language model using QLoRA.

## 🚀 Features
- 🔍 Semantic search over biomedical texts using FAISS
- 🤖 Answer generation via fine-tuned Mistral-7B (QLoRA)
- 🏥 Evaluated on both general and breast cancer Q&A datasets using BERTScore
- 🖥️ Clean and responsive Gradio-based chatbot interface [Live link - https://3e7a084c5a55830ef7.gradio.live/]
  
## 📚 Data Sources
This system retrieves and answers questions using a curated and diverse biomedical corpus, including:

- **[MedQuAD Q&A Dataset](https://huggingface.co/datasets/keivalya/MedQuad-MedicalQnADataset)** – Used for QLoRA fine-tuning.
- **PubMed Articles** – Web-scraped abstracts and full texts focused on general and breast cancer literature.
- **[Gale Encyclopedia of Medicine]** – Processed and indexed for general retrieval.
- **Breast Cancer Subset** – A domain-specific retrieval corpus built by scraping and indexing peer-reviewed articles on breast cancer using NLTK-based sentence-aware chunking.

All data sources were preprocessed into JSON/text chunks, embedded using `multi-qa-MiniLM-L6-cos-v1`, and indexed with FAISS for fast semantic search.


## 🛠️ Technologies
- `transformers` + `peft` (for QLoRA)
- `sentence-transformers` (MiniLM embeddings)
- `faiss` for vector search
- `gradio` for UI 
- `BERTScore` for evaluation

## 📊 Results
| Setup                           | BERTScore (F1) |
|--------------------------------|----------------|
| Vanilla Mistral-7B             | 0.838          |
| RAG-Mistral-7B                 | 0.843          |
| RAG + QLoRA Fine-Tuned Model   | 0.88–0.90      |

