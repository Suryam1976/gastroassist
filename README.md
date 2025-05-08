# GastroAssist AI

GastroAssist is an intelligent Q&A system designed specifically for gastroenterologists. This system leverages advanced search technology and large language models to provide concise, source-traced answers to clinical questions.

<p align="center">
  <img src="./static/gastroassist-logo.svg" alt="GastroAssist Logo" width="600">
</p>

## 🌟 Key Features

- **Enhanced Knowledge Pipeline**: Uses Tavily Search → Tavily Extract → LLM Summarizer to deliver accurate information
- **Source traceability**: All information includes proper citation for clinical confidence
- **Intelligent medical reasoning**: Recognizes gastroenterology terminology and understands the intent behind clinical questions
- **Robust error handling**: Multi-tiered fallback mechanisms ensure reliable operation even when services are unavailable
- **Web and mobile interfaces**: Access from any device for seamless integration into clinical workflow

## 🚀 Quick Start Guide

### Prerequisites

Before you begin, please ensure you have the following installed:

- Python 3.11+ ([Download Python](https://www.python.org/downloads/))
- Node.js 18+ ([Download Node.js](https://nodejs.org/))
- Git ([Download Git](https://git-scm.com/downloads))

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-organization/gastroassist.git
   cd gastroassist
   ```

2. **Set up the backend**

   ```bash
   # Create and activate virtual environment
   # On Windows:
   python -m venv venv
   venv\Scripts\activate

   # On macOS/Linux:
   python3 -m venv venv
   source venv/bin/activate

   # Install dependencies
   pip install -r requirements.txt
   ```

3. **Configure environment variables**

   Create a `.env` file in the root directory:

   ```
   # API Keys - Get these from your account dashboards
   OPENAI_API_KEY=your_openai_api_key  # Get from: https://platform.openai.com/api-keys
   TAVILY_API_KEY=your_tavily_api_key  # Get from: https://tavily.com/dashboard

   # Database
   DATABASE_URL=sqlite:///./gastroassist.db

   # Server
   DEBUG=True
   ```

4. **Start the backend server**

   ```bash
   uvicorn app.main:app --reload
   ```

5. **Set up the frontend** (in a new terminal window)

   ```bash
   cd frontend
   npm install
   npm run dev
   ```

6. **Access the application**

   - Web interface: [http://localhost:3000](http://localhost:3000)
   - API documentation: [http://localhost:8000/docs](http://localhost:8000/docs)
   - API health check: [http://localhost:8000](http://localhost:8000)

7. **Run a test query** (optional)

   ```bash
   # Test the enhanced pipeline with a sample query
   python scripts/test_pipeline.py "What are the latest guidelines for H. pylori treatment?"
   ```

## 📚 Documentation

For more detailed information, please refer to:

- [System Architecture](./docs/architecture/system-overview.md)
- [Enhanced Pipeline](./docs/architecture/enhanced-pipeline.md)
- [Frontend-Backend Integration](./docs/architecture/frontend-backend-integration.md)
- [Manual Testing Guide](./docs/architecture/manual-testing-guide.md)
- [Development Roadmap](./docs/roadmap/technical_review_and_roadmap.md)
- [Troubleshooting](./docs/troubleshooting.md)

## 🛠️ Tech Stack

- **Backend**: Python, FastAPI
- **Frontend**: Next.js, React, TypeScript, Redux
- **Enhanced Pipeline**:
  - **Search**: Tavily Search API
  - **Extraction**: Tavily Search with Raw Content
  - **Summarization**: OpenAI GPT-3.5 Turbo with medical prompting
- **Error Handling**: Multi-tiered fallback mechanisms at each pipeline stage

## 🧪 Testing

GastroAssist includes both automated and manual testing capabilities:

- **Automated Testing**: Use the test_pipeline.py script to test the enhanced pipeline
- **Manual Testing**: Pre-defined gastroenterology questions in the manual_testing directory
- **API Testing**: Interactive API documentation at /docs endpoint

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](./docs/development/contributing.md) for more details.

## 📞 Need Help?

If you encounter any issues:

1. Check the [Troubleshooting Guide](./docs/troubleshooting.md)
2. Search for similar issues in our [GitHub repository](https://github.com/your-organization/gastroassist/issues)
3. Join our [Discord community](https://discord.gg/gastroassist) for developer support

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
