# SciBot - AI Chatbot for Research Paper Understanding 🤖

<p align="center">
  <img src="https://github.com/abdallaellaithy/SciBot-Researchers-Chatbot/blob/main/assets/image.jpg" alt="Usage Instructions">
</p>

## How to Use the Program

Follow the steps in the GIF below to learn how to use the program:

<p align="center">
  <img src="https://github.com/abdallaellaithy/SciBot-Researchers-Chatbot/blob/main/assets/DEPI.gif" alt="Usage Instructions">
</p>

<br />
<div align="center">
  <h3 align="center">SciBot</h3>

  <p align="center">
  An AI-powered chatbot to simplify research paper comprehension and enable interactive exploration of scientific content.
  <br />
  <br />
</p>

</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#core-functionalities">Core Functionalities</a></li>
    <li><a href="#technical-deep-dive">Technical Deep Dive</a>
        <ul>
            <li><a href="#data-collection-and-preprocessing">Data Collection and Preprocessing</a></li>
            <li><a href="#model-development">Model Development</a></li>
            <li><a href="#advanced-implementation-techniques">Advanced Implementation Techniques</a></li>
        </ul>
    </li>
    <li><a href="#mlops-and-deployment">MLOps and Deployment</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

The growing volume and complexity of academic research can make it difficult for students, researchers, and professionals to quickly grasp the key ideas and contributions of a scientific paper. Many struggle with unfamiliar terminology, dense writing, or the time constraints of staying updated with current literature.

SciBot addresses this challenge by providing an AI-powered chatbot that simplifies research paper comprehension and enables interactive exploration of its content. Upload a PDF research paper, and SciBot will automatically extract, organize, and present its contents in a clear, human-readable explanation. Beyond summarization, SciBot features a robust question-answering system, allowing users to ask detailed queries about the paper, with conversational memory for a coherent dialogue experience.

**Key Goals:**

* Provide simplified, section-wise explanations of research papers.
* Enable users to ask specific questions about the paper's content.
* Maintain conversational context for follow-up questions and natural interaction.

### Built With

SciBot leverages a powerful stack of modern AI and web technologies:

* Python 3.9+
* FastAPI
* LangChain
* Hugging Face Transformers
* Gemini API (LLM)
* PyMuPDF / PDFPlumber / PyPDF2
* FAISS
* HTML5, CSS3, JavaScript

## Getting Started

To get a local copy up and running, follow these steps.

### Prerequisites

Make sure you have:

* Python 3.9+
* pip
* Gemini API Key (from [Google AI Studio](https://aistudio.google.com/app/apikey))

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/abdallaellaithy/SciBot-Researchers-Chatbot.git
   cd SciBot-Researchers-Chatbot
   ```

2. **Create and activate a virtual environment:**

   ```bash
   python -m venv venv
   # Windows:
   venv\Scripts\activate
   # macOS/Linux:
   source venv/bin/activate
   ```

3. **Install the dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Create `.env` file:**

   ```env
   GEMINI_API_KEY="YOUR_API_KEY_HERE"
   ```

## Usage

1. **Start the FastAPI backend:**

   ```bash
   uvicorn main:app --reload
   ```

2. **Open your `index.html` file** in the browser.

3. **Upload a PDF** and explore:

   * Use the Explanation module for summaries.
   * Use the Chatbot module for detailed Q\&A.

## Core Functionalities

### 1. Explanation Module

* Summarizes Abstract, Introduction, Methodology, Results, Conclusion.
* Uses `gemini-1.5-flash-latest`.

### 2. RAG-Based QA

* Uses `all-MiniLM-L6-v2` for embedding.
* Gemini model for answers.
* LangChain's `ConversationalRetrievalChain`.

### 3. Conversational Memory

* Tracks chat history using `ConversationBufferMemory`.

## Technical Deep Dive

### Data Collection and Preprocessing

* Extracts text via PyMuPDF, PyPDF2.
* Detects sections with regex.
* Chunks text with overlap (1000 chars, 200 overlap).
* FAISS stores vectorized chunks.

### Model Development

* Explanation uses section-specific prompts.
* RAG handles semantic search and LLM-based answers.
* JSON parsing via `StructuredOutputParser`.

### Advanced Techniques

* Prompt engineering for clarity.
* Conversational memory for coherence.
* Semantic chunking to enhance context.

## MLOps and Deployment

Deployment considerations:

* Dockerize the backend.
* Use tools like Streamlit/FastAPI + Nginx for web app hosting.
* Secure `.env` keys with environment secrets.

## Roadmap

* [ ] Add multilingual support.
* [ ] Add OCR for scanned PDFs.
* [ ] UI enhancements and mobile responsiveness.
* [ ] Streamlit or React frontend.

## Contributing

Contributions are welcome! Fork the repo, make changes, and submit a pull request.

## Contact

**Abdalla Ellaithy**
📧 [abdallaellaithy@gmail.com](mailto:abdallaellaithy@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/abdallaellaithy)
💻 [GitHub](https://github.com/abdallaellaithy)

## Acknowledgments

Thanks to:

* LangChain and Hugging Face communities.
* Gemini API from Google for LLM access.
* FAISS for fast vector search.
* Python & Open Source contributors.

---
