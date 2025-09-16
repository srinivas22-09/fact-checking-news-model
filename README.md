Fact-Checking News Model
This project is a Python-based system designed to automatically fact-check claims against real-time news articles from the internet. It uses a multi-stage approach to retrieve, filter, and analyze web content to determine if a given claim is supported, refuted, or lacks sufficient evidence.

Key Features
Real-time Web Retrieval: Fetches relevant news headlines and snippets using search APIs (SerpAPI and Tavily) and then downloads the full article bodies for analysis.

Semantic Search & Reranking: Employs a bi-encoder model for initial, fast filtering of relevant documents and a more powerful cross-encoder for precise reranking, ensuring the most relevant evidence is prioritized.

Natural Language Inference (NLI): Uses a pre-trained NLI model to compare the claim against excerpts from the articles and classify the relationship as SUPPORTED, REFUTED, or NO_EVIDENCE.

Reproducible Pipeline: The entire workflow is encapsulated within a Jupyter Notebook, making it easy to run, understand, and reproduce the results.

How It Works
The system operates in a series of logical steps:

Search: It queries news search engines to find articles related to the input claim.

Download: It fetches the full text content of the most promising articles.

Filter & Rank: It uses a combination of semantic search and a cross-encoder to select the top-k most relevant articles.

Verify: It performs a fine-grained NLI check, comparing the claim against multiple chunks of text from the top-ranked articles to find the strongest evidence.

Output: It provides a final verdict (SUPPORTED, REFUTED, NO_EVIDENCE) along with the confidence score and the specific evidence chunk that led to the conclusion.

Tech Stack
Core Languages: Python

Machine Learning Libraries: transformers, sentence-transformers, torch

Data Handling: tqdm, numpy

Web Scraping: requests, trafilatura

Setup and Installation
Clone this repository to your local machine.

Navigate to the project directory.

Install the required dependencies using the requirements.txt file:

Bash

pip install -r requirements.txt
Open the Jupyter Notebook (model-that-fetches-news-from-internet.ipynb) and follow the instructions to set up your API keys (if you have them) and run the cells.
