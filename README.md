
# AI Service for Best Buy Application

This FastAPI application serves as the core AI service for the Best Buy application, leveraging OpenAI models via the [Semantic Kernel SDK](https://github.com/microsoft/semantic-kernel). It powers intelligent recommendations and image generation features used in various parts of the Best Buy ecosystem.

## Running the AI Service Locally

The AI Service is independent and only relies on OpenAI or Azure OpenAI endpoints. You can run it locally without any other services running.

### Prerequisites

- [Python 3](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- [OpenAI API Key](https://beta.openai.com/docs/developer-quickstart/your-api-keys)
- [Azure OpenAI API Key](https://azure.microsoft.com/products/cognitive-services/openai-service/)

### Running the Service

1. Clone the repository and navigate to the `ai-service` directory.
2. Run the following commands:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Configure environment variables
export USE_AZURE_OPENAI=True
export USE_AZURE_AD=True
export AZURE_OPENAI_API_VERSION=2024-02-15-preview
export AZURE_OPENAI_DEPLOYMENT_NAME=<your-deployment-name>
export AZURE_OPENAI_ENDPOINT=<your-endpoint>
export AZURE_OPENAI_DALLE_ENDPOINT=<your-dalle-endpoint>
export OPENAI_API_KEY=<your-api-key>
export OPENAI_ORG_ID=<your-org-id>

# Start the application
uvicorn main:app --host 127.0.0.1 --port 5001
```

3. Once started, the server will run at `http://127.0.0.1:5001`.

### Testing the API

Use the `test-ai-service.http` file in the repository with VS Code and the [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) extension to test the API endpoints.
    