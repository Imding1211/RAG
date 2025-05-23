<a id="readme-top"></a>
# RAG（Retrieval-Augmented Generation）


<ol>
  <li><a href="#about-the-project">About The Project</a></li>
  <li><a href="#built-with">Built With</a></li>
  <li><a href="#getting-started">Getting Started</a></li>
  <li><a href="#usage">Usage</a></li>
  <li><a href="#references">References</a></li>
</ol>

## About The Project

This project demonstrates a Retrieval-Augmented Generation (RAG) system utilizing the latest Language Model (LLM) technologies. By leveraging PDF documents as the data source, ChromaDB as the database for efficient retrieval, and Gemma2 2B for language modeling, this project aims to provide high-quality, contextually relevant responses. The embedding model used is All-minilm, deployed by SBERT, ensuring robust vector representations of the data.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Built With

* LangChain
* ChromaDB
* Gemma2 2B
* all-MiniLM
  
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

To get a local copy up and running, follow these simple steps.

1. Create a new conda environment
   ```sh
   conda create --name RAG python=3.11
   ```
   
2. Activate environment
   ```sh
   conda activate RAG_LLM
   ```

3. Clone the repo
   ```sh
   git clone https://github.com/Imding1211/RAG.git
   ```
   
4. Change directory
   ```sh
   cd RAG
   ```
   
5. Install the required Python packages
   ```sh
   pip install -r requirements.txt
   ```
   
6. You can install Ollama directly on your computer or build it using Docker as well.
   * [On your computer](https://ollama.com/download)
   * [Using Docker](https://hub.docker.com/r/ollama/ollama)

   If you use Docker to build it, all subsequent commands related to Ollama need to be prefixed with the following command.
   ```
   docker exec -it <container name> ollama <command>
   ```
   Where `container name` should be replaced with your container's name.

7. Activate Ollama
   ```sh
   ollama serve
   ```
   You can open the browser and enter http://127.0.0.1:11434 to check if the Ollama server is operating normally.

8. Download the LLM
   ```sh
   ollama pull gemma2:2b
   ```

9. Download the embedding model
   ```sh
   ollama pull all-minilm
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

* Place the PDF to be read into the data folder.

* When running it for the first time, you need to create the ChromaDB database first.
   ```sh
   python main.py populate
   ```

* After creating the database, you can start the program using the following command.
   ```sh
   python main.py run
   ```

* You can use the following example questions to test if the program is running successfully.
   ```
   What hardware setup was used for training this models?
   ```
   
* When the following message appears, it means the program is running successfully.
   ```
   1 machine with 8 NVIDIA P100 GPUs.
   ```
   
* You can place your PDF files into the "data" folder, and run the following command to populate data to the database.
   ```sh
   python main.py populate
   ```

* Or you can rebuild the database using the following command.
   ```sh
   python main.py populate --reset
  ```

* You can clear the database using the following command.
   ```sh
   python main.py clear
  ```
   
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## References

[rag-tutorial-v2](https://github.com/pixegami/rag-tutorial-v2)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
