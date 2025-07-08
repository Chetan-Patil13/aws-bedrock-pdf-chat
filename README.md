# Chat With PDF - Generative AI Application
## Built Using Amazon Bedrock, Langchain, Python, Docker, Amazon S3, Amazon EC2
## Models used:
    Amazon Titan Embedding G1 - Text
    Anthropic Claude 2.1
---

## 🚀 Features

- 📄 Upload PDFs via Admin portal
- 🔍 Splits and embeds documents using **Titan Embeddings**
- 🧠 Vector search with **FAISS**
- 💬 Ask questions via User interface (PDF Q&A)
- ☁️ Uses **Amazon Bedrock** for embeddings & generation
- 🐳 Dockerized for easy deployment
- 🌐 Publicly accessible via EC2 instance

---

## 🔧 Tech Stack

| Tool               | Purpose                          |
|--------------------|----------------------------------|
| **LangChain**      | Document parsing, RAG pipeline   |
| **Amazon Bedrock** | Embeddings + LLM inference       |
| **FAISS**          | Vector similarity search         |
| **Streamlit**      | Frontend UI                      |
| **Docker**         | Containerization & portability   |
| **AWS EC2**        | Hosting                          |
| **AWS S3**         | Cloud storage for files & vector |

---

## 🖼️ Architecture

![image](https://github.com/user-attachments/assets/8c6a67ea-9786-4dc0-ac21-8c44204374d7)


## 📂 Folder Structure

aws-bedrock-pdf-chat/
├── Admin/
│ ├── admin.py
│ ├── Dockerfile
│ └── requirements.txt
├── User/
│ ├── app.py
│ ├── Dockerfile
│ └── requirements.txt
└── README.md


## 🛠️ Setup Instructions

### 🔨 Build Docker Images

```bash
# Admin App
cd Admin
docker build -t pdf-reader-admin .

# User App
cd ../User
docker build -t pdf-reader-user .
🚀 Run Docker Containers
Replace XXX, YYY, and your-bucket with actual values.


# Admin App (8083)
docker run -d \
  -e BUCKET_NAME=your-bucket \
  -e AWS_ACCESS_KEY_ID=XXX \
  -e AWS_SECRET_ACCESS_KEY=YYY \
  -e AWS_REGION=us-east-1 \
  -p 8083:8083 \
  pdf-reader-admin

# User App (8084)
docker run -d \
  -e BUCKET_NAME=your-bucket \
  -e AWS_ACCESS_KEY_ID=XXX \
  -e AWS_SECRET_ACCESS_KEY=YYY \
  -e AWS_REGION=us-east-1 \
  -p 8084:8084 \
  pdf-reader-user

```
##🌍 Deployed URLs
App	URL (kept empty to avoid billing issue)
Admin App	http://<your-ec2-ip>:8083
User App	http://<your-ec2-ip>:8084


##✨ Future Enhancements
✅ Use OpenSearch or Pinecone instead of FAISS

✅ Auth for Admin panel

✅ Document summarization using LLMs

✅ React-based frontend with FastAPI backend

✅ HTTPS & domain with Nginx and SSL

##📜 License
This project is open-source and available under the MIT License.

##👋 Connect
Built with ❤️ by Chetan Patil
