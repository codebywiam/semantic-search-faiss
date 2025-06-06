# Semantic Search Engine with USE & FAISS

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/codebywiam/semantic-search-faiss/blob/master/semantic_search_use_faiss.ipynb)

A powerful semantic search engine that leverages Google's Universal Sentence Encoder (USE) for generating meaningful text embeddings and Facebook's FAISS library for blazingly fast similarity search. This project demonstrates how to go beyond keyword matching to find documents based on their contextual meaning.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [How It Works](#how-it-works)
- [Tech Stack](#tech-stack)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview
Traditional search systems rely heavily on keyword matching, which can often miss relevant documents that don't contain the exact query terms. Semantic search addresses this by understanding the intent and contextual meaning of the user's query. This project implements a semantic search pipeline using the 20 Newsgroups dataset as a sample corpus.

## Features
- **Semantic Understanding:** Finds documents semantically similar to the query, not just keyword matches.
- **Efficient Search:** Utilizes FAISS for fast nearest neighbor search in high-dimensional vector space.
- **Pre-trained Embeddings:** Employs the Universal Sentence Encoder for robust text representations.

## How It Works
1.  **Data Loading & Preprocessing:** Text data (e.g., 20 Newsgroups dataset) is loaded and cleaned (removing headers, special characters, converting to lowercase).
2.  **Text Embedding:** Each preprocessed document is converted into a 512-dimensional vector using the Universal Sentence Encoder. These vectors capture the semantic meaning of the text.
3.  **FAISS Indexing:** The document embeddings are added to a FAISS index (`IndexFlatL2`), which allows for efficient similarity search.
4.  **Querying:**
    *   A user's query is preprocessed and embedded using the same USE model.
    *   FAISS searches the index for the `k` document vectors most similar (closest in L2 distance) to the query vector.
    *   The corresponding original documents are retrieved and displayed.

## Tech Stack
- Python 3.x
- TensorFlow & TensorFlow Hub (for Universal Sentence Encoder)
- FAISS (for similarity search)

## Setup and Installation

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/codebywiam/blob/master/semantic_search_use_faiss.ipynb)

## Project structure

```
semantic-search-faiss/
│
├── semantic_search_use_faiss.ipynb     # Jupyter Notebook with full pipeline
├── LICENSE                   # License file
└── README.md            # README.md

```
## Future Enhancements

- Build a Streamlit or Flask web interface for user interaction
- Implement more advanced preprocessing (e.g., stop word removal, lemmatization) and make it configurable.
- Experiment with different FAISS index types (e.g., IndexIVFFlat) for larger datasets.

## Acknowledgements

- The 20 Newsgroups dataset.
- Google for the Universal Sentence Encoder.
- Facebook AI Research for FAISS.
- Allow document upload or dynamic corpus extension.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
