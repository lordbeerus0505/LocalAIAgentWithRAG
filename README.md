# LocalAIAgentWithRAG
Find the video [here](https://www.youtube.com/watch?v=E4l91XKQSgw&ab_channel=TechWithTim)

# Steps at a high level
1. Create virtual env - `python3 -m venv ./venv`
2. Activate venv - `source venv/bin/activate` on MacOS
3. Install [Ollama](https://ollama.com/) then get the following models:
    * ollama pull llama3.2
    * ollama pull mxbai-embed-large
    We need both a language model and an embedding model.
4. Look at main.py - This describes the Llama model and a prompt for it. The line `reviews = retriever.invoke(question)` makes a call to the vector DB in vector.py and gets a response.
5. Look at vector.py - This uses ChromaDB to perform vector searching. We load the `mxbai-embed-large` model to use with the dataframe created from the CSV provided.
6. Chroma DB is stored on disk as a file, we provide the path to this as `./chrome_langchain_db`. Every time a retrival request is made the top 5 matching reviews are returned based on a similarity sesarch metric.


