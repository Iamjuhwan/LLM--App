# Simple LLM API

This project is a simple API application that leverages large language models (LLMs) to generate responses to user queries. The application uses FastAPI and interacts with the Groq API for LLM-based completions.

## Features

- **Multiple LLM Models**: Choose from a variety of models like `llama-3.1-405b-reasoning`, `llama-3.1-70b-versatile`, `llama-3.1-8b-instant`, and `mixtral-8x7b-32768`.
- **Customizable Output**: Adjust the `temperature` parameter to control the randomness and creativity of the responses.
- **Health Check Endpoint**: Quickly check if the API runs via the `/healthz` endpoint.

## Requirements

- Python 3.7+
- `fastapi`
- `uvicorn`
- `groq`
- `python-dotenv`

## Setup

1. **Clone the repository**:
    ```sh
    git clone <your-repository-url>
    cd <your-repository-directory>
    ```

2. **Install the dependencies**:
    ```sh
    pip install -r requirements.txt
    ```

3. **Set up environment variables**:
    Create a `.env` file in the root of the project and add your Groq API key:
    ```sh
    GROQ_API_KEY=your_api_key_here
    ```

4. **Run the application**:
    ```sh
    uvicorn app:app --reload
    ```

    This will start the FastAPI application, and it will be accessible at `http://127.0.0.1:8000`.

## API Endpoints

### Health Check

- **Endpoint**: `/healthz`
- **Method**: `GET`
- **Description**: Returns the status of the application.

### Chat Generation

- **Endpoint**: `/chat`
- **Method**: `POST`
- **Request Body**:
    ```json
    {
        "model": "llama-3.1-70b-versatile",
        "question": "Which is bigger, 9.11 or 9.9?",
        "temperature": 0.5
    }
    ```
- **Response**:
    ```json
    {
        "status": "success",
        "response": "9.9 is bigger."
    }
    ```
