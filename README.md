# Speech-to-Text API

This project provides a FastAPI-based web service to convert audio files to text using the SpeechRecognition library.

## Features

- Convert various audio formats (MP3, WAV, etc.) to text.
- Support for multiple languages (currently set to Thai).
- Update speech recognition engine and language dynamically via API.
- Support for both file upload and base64 encoded audio input.

## Requirements

- Python 3.9+
- FastAPI
- SpeechRecognition
- PyDub
- MoviePy

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/PongpreechaSuea/Speech2Text.git
    cd Speech2Text
    ```

2. Create a virtual environment and activate it:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use venv\Scripts\activate
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

## Configuration

Update the config.py file with your desired settings:

- Speech recognition engine
- Default language
- File paths for temporary storage
- Server host and port

## Usage

1. Start the server:
python app.py
Copy
2. The API will be available at `http://localhost:3000` (or the port you configured)

3. Use the following endpoints:
- `GET /`: Get API information
- `PUT /v1/api/using/engine`: Update speech-to-text engine
- `PUT /v1/api/using/language`: Update speech-to-text language
- `POST /v1/api/using/speech2text`: Convert speech to text (file upload)
- `POST /v1/api/using_base64/speech2text_base64`: Convert speech to text (base64 encoded audio)

## API Documentation

Once the server is running, you can access the API documentation at `http://localhost:3000/docs`

## Examples

### Convert audio file to text

```python
import requests

url = "http://localhost:3000/v1/api/using/speech2text"
files = {"file": open("audio.mp3", "rb")}
response = requests.post(url, files=files)
print(response.json())
```

<p align="center">
  <img src="images/image1.png" alt="Speech-to-Text API Overview" width="800">
</p>
