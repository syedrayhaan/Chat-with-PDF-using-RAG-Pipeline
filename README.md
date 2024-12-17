# Chat-with-PDF-using-RAG-Pipeline

## **Overview**  
This project implements a **Retrieval-Augmented Generation (RAG)** system that allows users to interact with PDF documents through natural language queries. By combining document processing, vector-based retrieval, and state-of-the-art language models, the system efficiently extracts relevant information and generates accurate responses from uploaded PDF files.  

---

## **Features**  
- **PDF Upload and Processing**: Upload single or multiple PDF files using a user-friendly Streamlit interface.  
- **Efficient Text Chunking**: PDF content is split into manageable chunks for better searchability.  
- **Vector Database Storage**: Text embeddings are stored and retrieved using **FAISS** for efficient similarity search.  
- **Natural Language Query**: Ask questions in plain English, and get relevant answers based on PDF content.  
- **Claude-3 Integration**: Leverages Anthropic’s Claude-3 API to generate well-structured responses based on the retrieved content.  

---

## **Tech Stack**  
The following tools and technologies were used in this project:  

| **Component**              | **Technology**                       |  
|----------------------------|--------------------------------------|  
| **Web Interface**          | Streamlit                           |  
| **PDF Text Extraction**    | PyPDF2                              |  
| **Text Chunking**          | LangChain (RecursiveCharacterTextSplitter) |  
| **Embeddings**             | spaCy (`en_core_web_sm`)            |  
| **Vector Store**           | FAISS (Facebook AI Similarity Search) |  
| **Language Model**         | Claude-3 API (Anthropic)            |  
| **Environment Management** | Python + Virtual Environment        |  

---

## **How It Works**  
1. **PDF Upload**: Users upload their PDF documents using the Streamlit sidebar.  
2. **Text Processing**:  
   - Text is extracted from PDFs using **PyPDF2**.  
   - Extracted text is split into chunks of 1000 characters with 200-character overlaps using LangChain.  
3. **Vector Database**: Text chunks are embedded using spaCy embeddings and stored in a FAISS vector database for similarity search.  
4. **User Query**: The user enters a question via the text input box.  
5. **Retrieval and Generation**:  
   - Relevant chunks are retrieved from FAISS using a retriever tool.  
   - The **Claude-3** language model generates a detailed response based on the retrieved content.  
6. **Output**: The response is displayed on the Streamlit interface.

---

## **Installation and Setup**  

### **Prerequisites**  
- Python 3.8 or higher  
- Anthropic Claude-3 API key  

### **Step 1: Clone the Repository**  
```bash
git clone https://github.com/yourusername/project-name.git
cd project-name
```

### **Step 2: Set Up the Environment**  
Create and activate a virtual environment:  
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

Install the required dependencies:  
```bash
pip install -r requirements.txt
```

### **Step 3: Set Up Environment Variables**  
Create a `.env` file and add your Claude-3 API key:  
```env
ANTHROPIC_API_KEY=your_anthropic_api_key_here
```

### **Step 4: Run the Application**  
Start the Streamlit app:  
```bash
streamlit run app.py
```

---

## **Usage**  
1. Open the Streamlit interface in your browser (usually at `http://localhost:8501`).  
2. Upload your PDF files via the sidebar.  
3. Click “Submit & Process” to extract and store PDF content.  
4. Ask questions about the uploaded PDFs using the text input box.  
5. View the generated responses based on your queries.  

---

## **Demo**  
Here’s a quick example of how the system works:  

1. **Upload**: Upload a research paper PDF.  
2. **Query**: Ask, “What are the key points in this document?”  
3. **Output**:  
   - Retrieves the most relevant sections of the document.  
   - Generates a concise answer using the Claude-3 language model.  

---

## **Project Outcomes**  
- Efficiently retrieves and summarizes content from large PDFs.  
- Reduces manual searching time and improves productivity.  
- Scalable for handling multiple PDF files and large volumes of data.  

---

## **Future Improvements**  
- Add support for other file formats (e.g., Word, Excel).  
- Implement a file management system to save and organize uploaded PDFs.  
- Enhance the UI/UX for a smoother user experience.  
- Integrate additional language models (e.g., GPT-4).  

---
