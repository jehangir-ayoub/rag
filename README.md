FAISS-based PDF Document Embedding and Search with LangChain and Google Generative AI

This project provides a powerful document retrieval system by embedding text from PDF documents into a FAISS vector store. The embeddings, created using Google Generative AI, allow users to perform efficient similarity-based searches and question-answering on document contents via a Streamlit interface. This setup is ideal for document-heavy applications requiring fast and scalable information retrieval.

Key Features PDF Text Extraction:
Extracts all text content from uploaded PDF files, regardless of length or structure. Text Splitting: Utilizes RecursiveCharacterTextSplitter to divide text into manageable chunks, which improves embedding quality and search precision. Embedding with Google Generative AI: Leverages Google Generative AI embeddings for high-quality vector representations. FAISS Vector Database: Efficient storage and search capabilities using FAISS (Facebook AI Similarity Search), ideal for handling large volumes of text data. Streamlit Interactive Interface: Provides a user-friendly interface for document upload, embedding, and natural language search queries. Architecture Overview PDF Upload: Users upload one or multiple PDF documents. Text Extraction and Chunking: Text is extracted from each PDF and split into chunks (based on size and overlap settings). Embedding and Vector Storage: Each text chunk is embedded using Google Generative AI, and the embeddings are stored in a FAISS vector database. Query and Retrieval: Users can input queries in natural language. The system searches the FAISS database for the most relevant chunks and returns answers.

Installation Prerequisites Python 3.8 or higher Google API key for Generative AI embeddings

Steps Clone the repository: git clone https://github.com/jehangir-ayoub/rag     
#click on the link to get the code from github 

Install dependencies:
Install the required Python packages listed in requirements.txt: pip install -r requirements.txt

Set up Google API Key: 
Add your Google API key to a .env file in the root directory. This key is necessary for embedding generation: GOOGLE_API_KEY=your_google_api_key

Run the application: Start the Streamlit server to access the interactive interface: streamlit run filename.py

Upload PDF Files: Use the interface to upload one or multiple PDF documents. The system will process and store them in the FAISS vector database.

Enter Queries: Once the documents are processed, type a question or keyword query in the provided field. The system will retrieve the most relevant chunks based on semantic similarity.

Example Workflow Upload a PDF with research papers, articles, or any document you want to search. Ask a Question like, “What are the main findings?” or “How does this compare to previous studies?” The system returns relevant text chunks and answers based on the content, ensuring you find pertinent information quickly.

Code Structure get_pdf_text(pdf_docs):
Extracts all text from PDF pages. get_text_chunks(text): Splits extracted text into overlapping chunks using RecursiveCharacterTextSplitter to ensure no important information is lost. get_vector_store(text_chunks): Embeds each chunk and stores it in the FAISS vector database. answer_query(query, vector_store): Retrieves the most relevant information based on user queries by searching the FAISS database.

Dependencies The following libraries are required and should be installed from requirements.txt: 
streamlit: For building the interactive web interface. PyPDF2: For reading and extracting text from PDF files. langchain: Used for chunking and question-answering chains. google.generativeai: Provides embedding capabilities for text chunks. faiss-cpu: For vector storage and efficient similarity search. python-dotenv: Loads the Google API key from .env. Future Enhancements Multi-Format Document Support: Support for other document types (e.g., Word, text files). Enhanced Retrieval Models: Use different embedding models or hybrid retrieval methods. User Authentication: Add authentication to secure access to sensitive document content.

Contributing We welcome contributions! Please feel free to fork the repository and submit a pull request with your improvements. Before contributing, please review our contribution guidelines in CONTRIBUTING.md (if available).

License This project is licensed under the MIT License. See the LICENSE file for details.
