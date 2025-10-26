🌞 Hyperion — The AI-Powered Energy Insight Engine

<p align="center">
  <img src="frontend/public/hyperion-logo.png" alt="Hyperion Logo" width="400"/>
</p>


Hyperion is an open-source, full-stack data intelligence platform that transforms raw, unstructured energy and sustainability data into real-time, actionable insights using AI, ETL pipelines, and cloud deployment.

It automates the analysis of CSVs, reports, and sensor data — providing clean dashboards and LLM-generated summaries that help organizations make faster, greener decisions.

🚀 Features

⚡ AI-Driven Analysis — LangChain + OpenAI for natural-language summaries and recommendations

📊 Data Forecasting — Prophet / scikit-learn models for trend prediction

☁️ AWS ETL Pipeline — Automated ingestion + cleaning via S3 & Lambda

🧩 Modern Backend — FastAPI microservice architecture with REST endpoints

💻 Interactive Frontend — Next.js + TypeScript dashboard for visualization

🧠 Vector Database — ChromaDB integration for document retrieval and context memory

🔒 Dockerized Deployment — Easily scalable with ECS, Render, or Docker Compose

🧠 Tech Stack
Layer	Tools / Frameworks
Frontend	Next.js · TypeScript · Tailwind CSS
Backend	FastAPI · Python · LangChain · OpenAI API
Data / AI	Pandas · ChromaDB · Prophet · scikit-learn
Cloud / Infra	AWS (S3, Lambda, ECS) · Docker · GitHub Actions
Other	Python-dotenv · Boto3 · Uvicorn
⚙️ Architecture Overview
+------------------------------------------------------+
|                     Frontend (Next.js)               |
|      → User uploads data / views insights            |
+---------------------------▲--------------------------+
                            |
                            ▼
+------------------- FastAPI Backend ------------------+
| /summarize_report  /forecast  /compare_sites         |
| Integrates LangChain → LLM → ChromaDB → AWS ETL      |
+---------------------------▲--------------------------+
                            |
                            ▼
+------------------- Data & Storage Layer --------------+
|  AWS S3 | PostgreSQL | ChromaDB | Pandas Pipelines   |
+------------------------------------------------------+

🧩 Setup Instructions
1. Clone the Repo
git clone https://github.com/gauravn17/Hyperion.git
cd Hyperion

2. Backend Setup
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
touch .env


Add the following to .env:

OPENAI_API_KEY=your_api_key_here
AWS_ACCESS_KEY_ID=your_aws_key
AWS_SECRET_ACCESS_KEY=your_aws_secret


Run the server:

uvicorn app:app --reload

3. Frontend Setup
cd ../frontend
npm install
npm run dev


Open http://localhost:3000
 in your browser.

🧪 Example Usage

Upload a CSV like:

Date,Energy_Produced,CO2_Emitted
2025-10-01,1200,340
2025-10-02,1350,330
2025-10-03,1500,325


Then call:

curl -X POST "http://127.0.0.1:8000/summarize_report/" -F "file=@sample.csv"


✅ Output:

{
  "summary": "Energy production increased steadily while CO₂ emissions declined, suggesting improved efficiency.",
  "metrics": {...}
}

📈 Roadmap

 Add time-series forecasting endpoint

 Deploy Dockerized microservice on AWS ECS

 Integrate ChromaDB vector search for long-term insights

 Build interactive sustainability dashboard (Next.js)

 Implement automated ETL pipeline with Lambda

👨‍💻 Developer

Gaurav Nair
📍 UC San Diego · Math-CS Major
🔗 LinkedIn
 · GitHub
