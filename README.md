# Sign Language to Voice AI

A real-time computer vision application that recognizes hand gestures through a webcam and converts recognized sign-language words into spoken output.

## Features

- Real-time hand tracking using MediaPipe
- Webcam-based gesture recognition with OpenCV
- Recognition of core sign-language gestures
- Word-by-word sentence construction
- Text-to-speech output using `pyttsx3`
- AI-assisted sentence processing through the Anthropic API
- Optional facial-emotion detection with DeepFace
- Keyboard controls for clearing, completing, and exiting the session
- Environment-variable based API key configuration
- No API keys or secrets stored in the source code

## Supported Core Signs

| Gesture | Recognized Word |
|---|---|
| Open hand | TECHNOLOGY |
| Peace/V sign | USE |
| Pointing index finger | FOR |
| Thumbs up | HELP |
| Index + pinky | NOT |
| Closed fist | WAR |

Additional vocabulary is also included in the application for sentence construction.

## How It Works

```text
Webcam
   ↓
OpenCV Frame Capture
   ↓
MediaPipe Hand Tracking
   ↓
Hand Landmark Analysis
   ↓
Gesture Recognition
   ↓
Word Sequence
   ↓
AI Sentence Processing
   ↓
Text-to-Speech
````

## Technology Stack

* **Python**
* **OpenCV** — webcam capture and computer vision
* **MediaPipe** — real-time hand landmark detection
* **NumPy** — numerical processing
* **pyttsx3** — text-to-speech
* **DeepFace** — optional facial-emotion analysis
* **Requests** — API communication
* **Anthropic API** — AI-assisted language processing

## Requirements

* Python 3.11 recommended
* Webcam
* Windows, macOS, or Linux
* Internet connection for AI-assisted processing
* Anthropic API key for AI features

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/Sehrabx/sign-language-to-voice-ai.git
cd sign-language-to-voice-ai
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the API key

Copy `.env.example` and configure your environment variable.

On Windows PowerShell:

```powershell
$env:ANTHROPIC_API_KEY="your_api_key_here"
```

Do not commit your real API key to GitHub.

### 5. Run the application

```bash
python sign_language_voice.py
```

## Controls

| Key   | Action                     |
| ----- | -------------------------- |
| `C`   | Clear the current sentence |
| `Q`   | Quit the application       |
| `ESC` | Quit the application       |

The application uses a short hold duration to confirm a detected gesture. After completing a sentence, the recognized text can be converted to speech.

## Project Structure

```text
sign-language-to-voice-ai/
│
├── sign_language_voice.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## Security

This project is designed so that sensitive API credentials are not stored in the source code.

* API keys are read from the `ANTHROPIC_API_KEY` environment variable.
* `.env` files are excluded through `.gitignore`.
* `.env.example` contains only a placeholder.
* Virtual environments and generated files are excluded from version control.

## Notes

The gesture recognition system is based on hand landmark patterns and is intended as a computer-vision demonstration rather than a complete interpretation of all sign languages.

Recognition accuracy can vary depending on lighting, camera quality, hand position, orientation, and background conditions.

## Future Improvements

* Expand the gesture vocabulary
* Improve recognition robustness across different users
* Add support for dynamic gestures
* Improve sentence generation and language processing
* Add configurable gesture mappings
* Package the application as a standalone desktop application
* Improve accessibility and multilingual speech support

