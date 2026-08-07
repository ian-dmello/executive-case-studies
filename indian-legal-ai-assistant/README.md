# Indian Legal AI Assistant

**Project Type:** AI Product Development | MSDS Capstone Project  
**Institution:** Northwestern University – Master of Science in Data Science  
**Domain:** Generative AI • Natural Language Processing • Legal Technology • Retrieval-Augmented Generation (RAG)

---

# Executive Summary

The Indian Legal AI Assistant was developed as the Capstone Project for the Master of Science in Data Science (MSDS) programme at Northwestern University.

The project was conceived to improve access to Indian laws by leveraging Artificial Intelligence and Natural Language Processing (NLP). Rather than expecting citizens to interpret complex legal language, the solution enables users to ask questions in plain language and receive simplified explanations of relevant statutory provisions and judicial decisions.

The application combines semantic search, Large Language Models (LLMs), document retrieval and multilingual translation to make Indian laws more understandable and accessible.

As part of the project team, I contributed to the design of the solution and **presented approximately 50% of the final Capstone presentation**, explaining the project vision, AI architecture, technical approach and expected business and social impact.

---

# Vision

**The common citizen should understand the rights, duties and responsibilities established under the Constitution and laws of India.**

---

# Mission

To simplify Indian laws and judicial decisions into language that is:

- Easy to understand.
- Legally meaningful.
- Accessible to non-lawyers.
- Available in multiple Indian languages.

---

# Business Problem

Indian legislation is typically written using complex legal terminology.

For many citizens this creates significant challenges in:

- Understanding legal rights.
- Understanding statutory obligations.
- Locating relevant legal provisions.
- Identifying applicable court judgments.
- Accessing reliable legal information without specialist assistance.

The project sought to bridge this gap through Artificial Intelligence.

---

# Proposed Solution

The application allows users to submit legal questions through a simple web interface.

The system is designed to:

1. Accept natural language legal queries.
2. Retrieve relevant statutory provisions.
3. Retrieve related judicial decisions.
4. Generate simplified explanations using NLP.
5. Provide references to applicable sections.
6. Translate responses into regional languages when required.

---

# Solution Architecture

```
User Query
      │
      ▼
Streamlit User Interface
      │
      ▼
Semantic Search Engine
      │
      ▼
Vector Database
      │
 ┌────┴────┐
 │         │
 ▼         ▼
Indian Laws   Case Judgments
 │         │
 └────┬────┘
      ▼
Large Language Model
      ▼
Plain Language Response
      ▼
English • Hindi • Tamil
```

---

# Project Methodology

The project followed a structured AI development lifecycle.

## Data Collection

Legal documents and judicial decisions were collected from publicly available sources.

Primary datasets included:

- Companies Act 2013
- Relevant judicial decisions
- Government publications
- Public legal databases

---

## Data Preparation

The project included:

- PDF extraction.
- Section identification.
- Text cleaning.
- Document segmentation.
- Metadata preparation.
- Data structuring for semantic retrieval.

Python libraries such as PyMuPDF, Pandas and Regular Expressions were used to prepare legal documents for downstream processing.

---

## Model Evaluation

Multiple transformer models were evaluated before selecting the final solution.

Models investigated included:

- T5 Small
- T5 Base
- Pegasus
- Facebook BART
- GPT-3.5
- GPT-based summarisation
- Additional transformer pipelines

Performance was assessed using established NLP evaluation metrics including:

- ROUGE
- BLEU

The selected models were further refined using manually generated reference outputs.

---

## Semantic Search

The application uses semantic search rather than traditional keyword matching.

Key technologies include:

- Sentence Transformers
- BERT Embeddings
- Pinecone Vector Database
- Semantic Similarity Search

This enables users to retrieve legally relevant sections even when queries do not exactly match statutory wording.

---

## User Interface

The solution includes a Streamlit-based web interface designed to provide:

- Simple legal queries.
- Plain-language responses.
- Expandable legal references.
- Relevant case law.
- Multilingual output.

The interface was designed to minimise the technical knowledge required to access legal information.

---

# Technology Stack

## Programming

- Python

## Artificial Intelligence

- Large Language Models (LLMs)
- Natural Language Processing
- Sentence Transformers
- Semantic Search
- Text Summarisation

## Machine Learning Libraries

- Transformers
- Scikit-learn
- SpaCy
- NLTK
- Gensim
- TextBlob

## Data Processing

- Pandas
- BeautifulSoup
- PyMuPDF
- SentencePiece

## Vector Search

- Pinecone
- Sentence Embeddings

## Application Framework

- Streamlit

---

# Key Features

- Natural language legal queries.
- Semantic search.
- Retrieval-Augmented responses.
- Plain-language explanations.
- Judicial decision retrieval.
- Statutory references.
- Expandable detailed explanations.
- Multilingual support.
- User-friendly interface.

---

# Multilingual Capability

The proposed solution supports legal explanations in:

- English
- Hindi
- Tamil

This improves accessibility for a broader population and aligns with the project's objective of increasing legal literacy.

---

# My Contribution

My contributions included:

- Participating in solution design.
- Supporting the NLP approach.
- Contributing to model evaluation.
- Assisting with semantic search design.
- Supporting multilingual solution planning.
- Preparing project documentation.
- Contributing to the final report.
- **Presenting approximately 50% of the final Capstone presentation**, covering the project vision, AI architecture, technical methodology and expected business impact.

---

# Skills Demonstrated

## Artificial Intelligence

- Generative AI
- Large Language Models
- Retrieval-Augmented Generation
- Prompt Engineering
- Semantic Search

---

## Natural Language Processing

- Document Summarisation
- Text Paraphrasing
- Semantic Similarity
- Question Answering
- Information Retrieval

---

## Software Engineering

- Python
- Streamlit
- Vector Databases
- API Integration
- Knowledge Retrieval

---

## Product Development

- Solution Architecture
- User Experience Design
- Product Vision
- Technical Communication
- Agile Team Collaboration

---

# Business & Social Value

The project demonstrates how Artificial Intelligence can make legal information more accessible to the general public.

Potential applications include:

- Citizen legal awareness.
- Government digital services.
- Educational institutions.
- Legal research.
- Small businesses.
- Public legal information portals.

By simplifying complex legislation into understandable language, the solution has the potential to improve legal literacy and encourage greater awareness of constitutional rights and responsibilities.

---

# Future Enhancements

Potential future enhancements include:

- Support for all major Indian languages.
- Voice-enabled legal assistant.
- Mobile application.
- AI-powered legal document drafting.
- Expanded legal knowledge base.
- Real-time legal updates.
- Explainable AI features.
- Integration with official legal databases.

---

# Repository Contents

- Streamlit application.
- NLP processing pipeline.
- Model evaluation notebooks.
- Fine-tuning scripts.
- Vector search implementation.
- Project report.
- Presentation.
- Training datasets.
- Model evaluation outputs.

---

# Disclaimer

This repository represents the Capstone Project completed as part of the Master of Science in Data Science programme at Northwestern University.

It demonstrates the application of Artificial Intelligence and Natural Language Processing to improve access to legal information and should not be interpreted as a substitute for professional legal advice.
