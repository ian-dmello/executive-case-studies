# AI-Powered Legal Language Paraphrasing

## Project Overview

An AI/NLP-based prototype designed to make complex Indian legal provisions and case judgments easier for non-specialists to understand.

The project focused on converting legal language into simpler, more accessible language and providing users with relevant legal information through a query-based interface. The solution also incorporated regional-language output in Hindi and Tamil.

The project was developed as part of the MSDS 498 Capstone Project in 2024.

---

## Business Problem

Indian laws and court judgments often contain complex legal terminology that can be difficult for non-specialists to interpret.

The objective was to explore whether Natural Language Processing (NLP) could be used to:

- Simplify complex legal language
- Make relevant legal provisions easier to understand
- Retrieve relevant legal content based on a user's query
- Provide information in regional languages
- Improve accessibility to legal information

---

## Project Scope

The initial solution focused on:

- Companies Act, 2013
- Relevant case judgments relating to the Companies Act
- NLP-based paraphrasing
- Semantic search
- Query-based retrieval
- Hindi and Tamil translation
- A user-facing chatbot interface

The dataset included the Companies Act, 2013 and 100 relevant case judgments.

---

## My Role

### Project Concept, Legal Data & AI/NLP Development

I originated the project concept and was primarily responsible for the business/domain side of the solution and the AI/NLP work.

My contribution included:

- Defining the problem and overall solution concept
- Identifying the use case for making Indian legal information more accessible
- Working with the Companies Act, 2013 and relevant case judgments
- Converting legal source material into structured data suitable for NLP processing
- Evaluating alternative NLP models
- Developing and testing paraphrasing approaches
- Working on model training and fine-tuning
- Comparing model outputs using evaluation metrics
- Contributing to the selection of the most appropriate models for the use case
- Working with the technical team member to integrate the AI component into the final application

### Team Collaboration

The application engineering and subsequent technical integration were primarily undertaken by my teammate, **Nitesh Yadav**, who had a Computer Science background.

His contribution included:

- Streamlit web interface
- Application integration
- Semantic search implementation
- Vectorization and search infrastructure
- Pinecone integration
- Query handling
- Translation integration
- End-to-end application functionality

The project was therefore a collaboration between **business/domain and AI/NLP development** and **application engineering**.

---

## Approach

The project followed an end-to-end process:

1. Define the problem and product concept
2. Collect legal source material
3. Extract and structure legal information
4. Evaluate alternative NLP models
5. Generate paraphrased legal content
6. Evaluate model performance
7. Prepare the selected output for semantic search
8. Develop the user query interface
9. Implement semantic retrieval
10. Provide Hindi and Tamil output
11. Test the end-to-end solution

---

## Data Preparation

Legal documents were processed programmatically using Python.

PyMuPDF was used to extract section titles and corresponding legal content from PDF documents. The extracted information was structured using Pandas for subsequent NLP processing.

The project also incorporated 100 relevant case judgments relating to the Companies Act.

---

## NLP & Model Evaluation

Multiple NLP approaches were investigated, including:

- T5-small
- T5-base
- BART
- DistilBART
- Pegasus
- BERT-based approaches
- ChatGPT-generated reference material
- Gemini-generated reference material

The models were evaluated based on their ability to produce paraphrased content while retaining the meaning of the original legal text.

The project used metrics including:

- Precision
- Recall
- F1 Score
- BERTScore
- ROUGE

Model performance varied depending on whether the task involved statutory provisions or case judgments.

For the law-section dataset, `google/pegasus-large` produced the strongest reported BERTScore among the tested models.

For the case-judgment dataset, `facebook/bart-large-cnn` produced the strongest reported result.

---

## Technology Stack

### Programming & Data

- Python
- Pandas
- PyMuPDF
- Regular Expressions

### NLP / Machine Learning

- Hugging Face Transformers
- T5
- BART
- Pegasus
- Sentence Transformers
- BERT-based embeddings

### Search & Retrieval

- Semantic Search
- Cosine Similarity
- Pinecone Vector Database

### Application

- Streamlit
- Python-based query interface

### Language & Accessibility

- English
- Hindi
- Tamil
- Google Translate
- Text-to-Speech

---

## Solution Architecture

The conceptual solution consisted of the following flow:

**Legal Documents → Data Extraction → NLP Models → Paraphrased Legal Content → Embeddings → Semantic Search → User Query → Relevant Legal Information → Translation / Output**

The application provided users with the ability to select the legal content type and output language before submitting a query.

---

## Key Results

The project successfully demonstrated an end-to-end prototype capable of:

- Processing legal source documents
- Generating simplified legal content
- Comparing multiple NLP models
- Retrieving relevant legal information through semantic search
- Providing a query-based user interface
- Producing output in Hindi and Tamil
- Testing the solution with independent users

The project demonstrated the practical potential of NLP in making complex legal information more accessible.

---

## Key Learning

The project provided practical exposure to the intersection of:

- Business/domain knowledge
- Data preparation
- Artificial Intelligence
- Natural Language Processing
- Machine Learning model evaluation
- Semantic search
- Application development
- Technology collaboration

A key learning was that successful AI projects require more than selecting a sophisticated model. **Data quality, domain understanding, model evaluation and integration into a usable workflow are equally important.**

---

## My Perspective

Coming from an accounting and finance background rather than a Computer Science background, this project provided an opportunity to work directly with AI/NLP technologies and understand how a business problem can be translated into a technology solution.

The project also reinforced the value of combining **domain expertise with technology capabilities**, rather than treating AI as a purely technical exercise.

---

## Future Opportunities

Potential extensions identified during the project included:

- Expanding coverage to additional central and state laws
- Adding more Indian regional languages
- Improving the underlying language models
- Supporting voice-based queries
- Enabling queries directly in regional languages
- Exploring more advanced LLM-based approaches

---

## Project Information

**Project:** MSDS 498 Capstone Project  
**Year:** 2024  
**Project:** AI/NLP-based Legal Language Paraphrasing  
**Domain:** Artificial Intelligence / Natural Language Processing / Legal Technology  
**Team:** Group 10

### Team

- Ian Dmello
- Nitesh Yadav
- Christopher Jayaprakash V
- Sumit Deb
- Vaibhav Mishra

---

> **Note:** This project was an academic prototype and should not be treated as a substitute for professional legal advice.
