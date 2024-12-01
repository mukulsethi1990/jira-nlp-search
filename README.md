# Jira NLP Search

A Natural Language Processing based search application for Jira issues. This application enhances Jira's search capabilities by using NLP techniques to find relevant issues based on natural language queries.

## Features

- Natural language search across Jira issues
- TF-IDF based similarity matching
- RESTful API interface
- Configurable search parameters
- Support for project-specific searches

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/jira-nlp-search.git
cd jira-nlp-search
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Configure environment variables:
```bash
cp .env.example .env
# Edit .env with your Jira credentials
```

## Usage

1. Start the API server:
```bash
uvicorn src.jira_nlp_search.api:app --reload
```

2. The API will be available at `http://localhost:8000`

3. Use the following endpoints:
   - POST `/refresh-index`: Refresh the search index
   - POST `/search`: Search for issues

### Example Search Request

```bash
curl -X POST "http://localhost:8000/search" \
     -H "Content-Type: application/json" \
     -d '{"query": "authentication issues in login page", "top_k": 5, "project_key": "PROJ"}'
```

## Configuration

Configure the application by setting the following environment variables in `.env`:

- `JIRA_URL`: Your Jira instance URL
- `JIRA_USERNAME`: Your Jira username/email
- `JIRA_API_TOKEN`: Your Jira API token

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.