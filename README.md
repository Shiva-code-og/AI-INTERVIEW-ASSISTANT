# AI Interview Assistant 🤖🎙️

An interactive, voice-based technical interview simulator that mimics a natural face-to-face coding interview. Powered by Google Gemini, LangChain, LangGraph, AssemblyAI, and Murf AI, the app conducts real-time adaptive interviews and provides detailed performance feedback.

---

## 🌟 Key Features

*   **Voice-to-Voice Interaction**: The entire interview is conducted via audio. You hear the interviewer ("Natalie") speak, and you record your answers using your microphone.
*   **Topic Selection**: Practice across multiple domains, including:
    *   Self Introduction
    *   Generative AI
    *   Python
    *   English
    *   HTML
    *   CSS
*   **Adaptive Conversational Flow**: Natalie asks **5 short, direct questions** that dynamically adapt to your actual answers. She will build on your explanations or simplify the questions if you struggle.
*   **Real-time Text-to-Speech Streaming**: Uses **Murf AI** (Natalie's voice model) to stream audio questions to the browser with minimal latency.
*   **Automated Speech-to-Text**: Transcribes your spoken answers using **AssemblyAI**'s transcription models.
*   **Detailed AI Feedback & Scoring**: At the end of the interview, receive a structured score (1-5), positive highlights based on your actual answers, and clear recommendations for improvement.

---

## 🛠️ Tech Stack

### Frontend
*   **HTML5 & CSS3**
*   **Tailwind CSS** (via CDN)
*   **FontAwesome Icons**
*   **Vanilla JavaScript** (Audio Recording via `MediaRecorder` API)

### Backend
*   **Python Flask** (Port `5001` with CORS enabled)
*   **LangChain / LangGraph**: Orchestrates the state, prompt management, and message memory.
*   **Google Gemini (via GenAI)**: Powers the conversational AI engine (`gemini-2.5-flash`).
*   **AssemblyAI**: Handles high-accuracy speech-to-text transcriptions.
*   **Murf AI**: Handles high-quality text-to-speech audio streaming.

---

## 📁 Repository Structure

```text
├── backend/
│   ├── app.py             # Flask server & LangChain logic
│   ├── requirements.txt   # Python dependencies
│   └── .env               # Local environment variables (ignored in Git)
├── frontend/
│   ├── index.html         # Interview UI dashboard (Tailwind CSS)
│   └── index.js           # Media recording & API request handling
└── .gitignore             # Git ignore configuration
```

---

## 🚀 Getting Started

### 1. Prerequisites & API Keys
You will need API keys from the following platforms:
1. **Google AI Studio**: For the Gemini API (`GOOGLE_API_KEY`)
2. **AssemblyAI**: For speech-to-text transcription (`ASSEMBLYAI_API_KEY`)
3. **Murf AI**: For text-to-speech streaming (`MURF_API_KEY`)

Create a `.env` file inside the `backend` directory:
```env
GOOGLE_API_KEY=your_gemini_api_key_here
ASSEMBLYAI_API_KEY=your_assemblyai_api_key_here
MURF_API_KEY=your_murf_api_key_here
```

### 2. Setup the Backend
1. Navigate to the `backend` directory.
2. Create and activate a Python virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the Flask server:
   ```bash
   python app.py
   ```
   *The server will run on `http://127.0.0.1:5001`.*

### 3. Run the Frontend
*   Simply open the `frontend/index.html` file in any modern web browser, or serve it using a local HTTP server extension (e.g., Live Server in VS Code).
