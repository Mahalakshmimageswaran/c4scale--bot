 AI-Powered Question Answering Agent

This Python-based AI agent crawls documentation from a given help website and answers user questions based on the content. It uses semantic search to find relevant information.

## How it Works

1.  **Crawling:** The agent recursively crawls the specified website (up to 50 links).
2.  **Indexing:** It extracts text content from the pages and creates semantic embeddings using `HuggingFaceEmbeddings`. These embeddings are stored in a `FAISS` vector store.
3.  **Searching:** When you ask a question, the agent embeds your query and searches the `FAISS` store for the most similar document snippets.
4.  **Answering:** The top relevant snippets, along with their similarity distance and source URL, are displayed if the distance is below a defined threshold. If no relevant information is found, it indicates so.

## Prerequisites

-   Python 3.x
-   Required Python libraries (install using `pip install -r requirements.txt`):
    -   `requests`
    -   `beautifulsoup4`
    -   `langchain-community`
    -   `langchain-huggingface`
    -   `faiss-cpu`
    -   `nltk`
    -   `numpy`

## Setup

1.  Clone the repository (if applicable).
2.  Install the required libraries: `pip install -r requirements.txt`
3.  Ensure you have an internet connection to crawl websites and download NLTK resources.

## Usage

1.  Run the `qa_agent.py` script: `python qa_agent.py`
2.  The agent will prompt you to "Enter the help website URL: ". Provide the starting URL of the documentation you want to query.
3.  After crawling and indexing, you can ask questions in the terminal.
4.  Type `exit` to quit the agent.

## Key Components

-   `crawl_website()`: Crawls the website.
-   `scrape_and_process()`: Extracts text from HTML.
-   `create_vectorstore()`: Creates the semantic index.
-   `semantic_search_agent()`: Handles user queries and retrieves answers.

## Configuration

-   `MAX_LINKS`: Maximum number of pages to crawl (default: 50).
-   `DISTANCE_THRESHOLD`: Threshold for determining if a retrieved document is relevant (adjust in `semantic_search_agent()`).

## Future Improvements

-   Answer generation using a Language Model (LLM).
-   More robust content extraction.
-   Context enrichment for better understanding.
-   Handling synonyms and different question intents.





