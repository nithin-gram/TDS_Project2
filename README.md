# Automated QA API

This API leverages cutting-edge AI models to provide intelligent responses to questions derived from course materials. Built with FastAPI, it offers seamless integration, real-time processing, and dynamic code execution.

## What This API Does
- **Understands Questions**: Processes natural language queries and determines the best approach to answering them.
- **Executes Code**: If a question requires computation, the system generates and runs Python or Bash scripts.
- **Handles File Inputs**: Accepts ZIP and CSV files, extracting relevant data to improve answer accuracy.

## How It Works
1. A user submits a question and, optionally, a file.
2. The system decides whether it can directly respond or if code execution is required.
3. If code execution is needed, Python or Bash scripts are generated and run in a controlled environment.
4. If a file is provided, its contents are parsed and factored into the response.
5. The answer is returned to the user.

## Technical Highlights
- **AI-Powered Processing**: Connects to external LLM APIs for context-aware responses.
- **Secure Execution**: Runs generated code in an isolated sandbox.
- **File Integration**: Extracts and processes ZIP/CSV files for enhanced understanding.
- **Optimized Performance**: Uses efficient algorithms to find similar questions and reduce redundant computations.

## Installation Guide
### Prerequisites
Ensure your environment meets the following:
- Python 3.8+
- FastAPI Framework
- scikit-learn
- dotenv for environment variables

### Steps to Set Up
1. Clone the repository:
   ```bash
   git clone https://github.com/nithin-gram/TDS_Project2.git
   cd Tds_Project2
   ```
2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Configure API keys in a `.env` file:
   ```plaintext
   GITHUB_API_KEY=your_api_key_here
   VERCEL_API_KEY=your_api_key_here
   ```
4. Start the API server:
   ```bash
   uvicorn app:app --reload
   ```

## Making API Requests
### Endpoint: `/api`
- **Method**: `POST`
- **Expected Input**:
  - `question`: A textual query (required).
  - `file`: An optional ZIP or CSV file.

#### Example Request
```bash
curl -X POST "http://localhost:8080/api/" \
  -H "Content-Type: multipart/form-data" \
  -F "question=How does pandas read a CSV file?" \
  -F "file=@data.csv"
```

## Handling Errors
Common failure scenarios include:
- Incorrectly formatted questions
- Errors in code execution
- Issues with file processing
- API response failures

## How to Contribute
Want to enhance this project? Follow these steps:
1. Fork the repo.
2. Create a new feature branch:
   ```bash
   git checkout -b new-feature
   ```
3. Make improvements and commit:
   ```bash
   git commit -m 'Implemented a new feature'
   ```
4. Push the branch:
   ```bash
   git push origin new-feature
   ```
5. Open a pull request.

## License
This project is licensed under MIT, allowing free and open use.

