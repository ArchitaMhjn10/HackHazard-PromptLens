# PromptLens

**AI-Powered Business Intelligence | Ask Questions. Get Dashboards.**

PromptLens is an intelligent data analytics platform that transforms plain-English business questions into interactive, multi-chart dashboards in seconds. No SQL knowledge required. No manual chart configuration. Just upload data and ask.

## 🎯 What It Does

PromptLens combines natural language processing with data intelligence to deliver:

- **Instant Dashboard Generation**: Ask a question, get interactive charts automatically
- **Schema-Aware Analysis**: Understands your data structure and generates accurate queries
- **Multi-Chart Intelligence**: Automatically selects the best chart types for your data
- **Natural Language Insights**: Results summarized in plain English, not technical jargon
- **CSV Upload Support**: Works with your own datasets or demo data
- **SQL Inspection**: View generated queries for transparency and trust

## 🚀 Getting Started

### Prerequisites

- **Node.js** 16+ (for frontend)
- **Python** 3.9+ (for backend)
- **Git**

### Quick Start

#### 1. Clone & Setup

```bash
git clone <repository-url>
cd promptlens
```

#### 2. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

The frontend will be available at `http://localhost:5173`

#### 3. Backend Setup

```bash
cd backend
python -m venv .venv

# On Windows:
.\.venv\Scripts\activate

# On macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
uvicorn app.main:app --reload
```

The backend API will be available at `http://localhost:8000`

### Accessing the Application

1. Open your browser to `http://localhost:5173`
2. Upload a CSV file or use the sample dataset
3. Ask a question about your data
4. View the generated dashboard and insights

## 📁 Project Structure

```
promptlens/
├── frontend/                    # React + TypeScript + Vite
│   ├── src/
│   │   ├── pages/             # Page components (Home, Demo, Docs, System)
│   │   ├── App.tsx            # Main application component
│   │   └── main.tsx           # Entry point
│   ├── package.json
│   ├── vite.config.ts
│   └── tsconfig.json
│
├── backend/                     # FastAPI + Python
│   ├── app/
│   │   ├── main.py            # FastAPI application & endpoints
│   │   └── data/
│   │       └── uploads/       # User uploaded files
│   ├── requirements.txt
│   └── README.md
│
├── docs/                        # Documentation
└── README.md                    # This file
```

## 🏗️ Architecture Overview

PromptLens follows a full-stack architecture:

### Frontend (React + TypeScript)
- **Upload Interface**: CSV file ingestion with validation
- **Query Interface**: Natural language input with history
- **Dashboard Rendering**: Multi-chart visualization using Recharts
- **SQL Inspector**: View and inspect generated queries
- **Responsive Design**: Desktop-first, dark theme with warm palette

### Backend (FastAPI)
- **File Handling**: Secure CSV upload and processing
- **Schema Detection**: Automatic type inference and schema analysis
- **LLM Pipeline**: Gemini-powered SQL generation and insights
- **Query Execution**: SQLite-based read-only query execution
- **Error Recovery**: Automatic SQL correction and retry logic

### Data Layer
- **SQLite**: In-memory or file-based dataset storage
- **Session Scoping**: Per-session data isolation
- **Read-Only Access**: Enforced through query guards

## 🔧 Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Frontend** | React 18, TypeScript, Vite, Tailwind CSS | Modern UI framework with fast builds |
| **Backend** | FastAPI, Python 3.9+ | High-performance async API |
| **Database** | SQLite | Lightweight, serverless data storage |
| **LLM** | Google Gemini | Schema-aware SQL & insight generation |
| **Visualization** | Recharts | Interactive, responsive charts |
| **Build** | Vite | Lightning-fast development & production builds |

## 📊 Key Features

### Data Upload
- Support for CSV files
- Automatic schema detection
- Type inference for columns
- Preview before analysis

### Intelligent Querying
- Natural language question parsing
- Schema-aware SQL generation
- Contextual chart type selection
- Multi-chart dashboard composition

### Results & Insights
- Interactive chart visualizations
- Plain English summaries
- SQL query inspection
- Follow-up query support with history

### Safety & Reliability
- Read-only query execution
- Hallucination guards
- Automatic error recovery
- Clear error messaging

## 🛠️ Development

### Running Tests

```bash
# Frontend tests
cd frontend
npm run test

# Backend tests
cd backend
pytest
```

### Building for Production

```bash
# Frontend
cd frontend
npm run build

# Backend
# Deploy using Docker or standard Python deployment
```

### Code Structure

- **Frontend**: Component-based React with TypeScript
- **Backend**: API-first FastAPI with modular endpoints
- **Configuration**: Environment-based settings

## 📚 Documentation

- [Frontend README](./frontend/README.md) - React app documentation
- [Backend README](./backend/README.md) - FastAPI setup and endpoints
- [Architecture Document](./_bmad-output/planning-artifacts/architecture.md) - Technical design decisions
- [Product Requirements](./_bmad-output/planning-artifacts/prd.md) - Full product specification

## 🤝 Contributing

1. Create a feature branch from `main`
2. Make your changes following the project structure
3. Test thoroughly before submitting
4. Create a pull request with clear description

## 📝 API Endpoints

### Health Check
```
GET /health
```

### File Upload
```
POST /upload
Content-Type: multipart/form-data
Body: file (CSV)
```

### Query Execution
```
POST /query
Content-Type: application/json
Body: { "question": "...", "dataset_id": "..." }
```

For complete API documentation, visit `http://localhost:8000/docs` when the backend is running.

## 🎓 Use Cases

- **Quick Data Exploration**: Analyze datasets without SQL knowledge
- **Business Reporting**: Generate reports from raw data in seconds
- **Data Debugging**: Investigate data issues with natural language queries
- **Executive Summaries**: Get key insights with visual context
- **Demo & Presentation**: Impress stakeholders with instant analytics

## ⚙️ Performance

- **Query Response Time**: < 3 seconds for typical datasets
- **Dashboard Rendering**: < 500ms for multi-chart layouts
- **File Upload**: Supports files up to 50MB
- **Concurrent Sessions**: Multiple users with isolated data contexts

## 🔒 Security

- **Read-Only Queries**: All database access is read-only
- **Session Isolation**: Each session has independent data scope
- **No Secrets in Code**: Environment-based configuration
- **Input Validation**: All user inputs validated before processing

## 📦 Deployment

### Local Development
See [Quick Start](#quick-start) above

### Docker Support
The project includes Docker-friendly setup for containerized deployment.

### Cloud Deployment
Can be deployed to major cloud platforms (AWS, GCP, Azure) with minimal configuration changes.

## 🐛 Troubleshooting

### Frontend won't load
- Ensure Node.js 16+ is installed: `node --version`
- Check that backend is running on `http://localhost:8000`
- Clear browser cache and try again

### Backend won't start
- Verify Python 3.9+ is installed: `python --version`
- Ensure all dependencies are installed: `pip install -r requirements.txt`
- Check that port 8000 is available

### CSV upload fails
- Verify CSV format (comma-separated values)
- Check file size (max 50MB)
- Ensure headers are present in first row
- Try with sample CSV from demo
**For more information**, visit the [documentation](./docs) folder or review the [architecture decisions document](./_bmad-output/planning-artifacts/architecture.md).
