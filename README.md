# A Llama3 based Conversational RAG that can take a pdf as input and answer your questions.

This is a simple RAG model that can take a pdf as input and answer your questions. It uses the Llama3 model from Ollama. It has a streamlit interface that can be used to interact with the model. First it takes the pdf file as input. It then extracts the text from the pdf file. Then it takes the query and first determines whether the query can can be answered without the document or not (In case it is greeting, valediction or simillar). If it can be answered without the document then it directly answers the query. If it can't be answered without the document then it uses the Llama3 model to answer the query.

It divides the document into chunks of 1000 words and then uses a vector database to store chunks. WHen it gets the query it first performs a search on the vector database to get the most relevant chunks. Then it uses the Llama3 model to answer the query, using the retrieved chunks and previous conversation history as context (This makes  it a conversational RAG model).

### Image of the interface
![Image of the interface](https://raw.githubusercontent.com/Shlok-Jain/RAG-based-pdf-question-answer/main/image.png)

## Installation
First install Ollama on your system from [https://ollama.com/](https://ollama.com/).
Then run the Llama3 model using follwoing command:
```bash
ollama run llama3
```

## Install packages
```bash
pip install streamlit
pip install pymupdf
pip install langchain
pip install langchain_community
pip install docarray
```

## Run the code
```bash
streamlit run main.py
```