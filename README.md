# Sentiment Analyzer (Mistral)

A real-time sentiment analysis application that uses the **Mistral model** via Ollama to classify text as Positive, Negative, or Neutral. The app features a clean web interface built with Streamlit and a robust API backend powered by FastAPI.

## Features

- 🚀 **FastAPI** backend with RESTful API endpoints
- 🎨 **Streamlit** frontend with intuitive user interface
- 🤖 **Ollama-hosted Mistral model** for accurate sentiment analysis
- ⚡ **Real-time analysis** with instant results
- 🔄 **Local deployment** - no external API keys required

## Architecture

```
├── backend/
│   └── main.py          # FastAPI server with sentiment analysis endpoint
├── frontend/
│   └── app.py          # Streamlit web interface
├── requirements.txt     # Python dependencies
└── README.md
```

## Prerequisites

- Python 3.8+
- [Ollama](https://ollama.ai/) installed and running
- Mistral model pulled in Ollama

## Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd sentiment-analyzer-mistral
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Install and setup Ollama**
   - Download and install Ollama from [ollama.ai](https://ollama.ai/)
   - Pull the Mistral model:
     ```bash
     ollama pull mistral
     ```

4. **Start the application**
   
   **Terminal 1 - Backend:**
   ```bash
   uvicorn backend.main:app --reload
   ```
   
   **Terminal 2 - Frontend:**
   ```bash
   streamlit run frontend/app.py
   ```

5. **Access the application**
   - Frontend: http://localhost:8501
   - API Documentation: http://localhost:8000/docs

## Usage

### Web Interface
1. Open your browser to `http://localhost:8501`
2. Enter text in the text area
3. Click "Analyze" to get sentiment prediction

### API Endpoint
```bash
curl -X POST "http://localhost:8000/analyze/" \
     -H "Content-Type: application/x-www-form-urlencoded" \
     -d "text=I love this product!"
```

Response:
```json
{
  "sentiment": "Positive"
}
```

## Technologies Used

- **Backend:** FastAPI, Uvicorn
- **Frontend:** Streamlit
- **AI Model:** Mistral via Ollama
- **HTTP Client:** Requests

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).
