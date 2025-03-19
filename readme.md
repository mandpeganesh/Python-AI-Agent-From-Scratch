# Python AI Agent From Scratch

A powerful AI research agent built with LangChain and Claude 3.5 Sonnet that generates comprehensive, structured research outputs from natural language queries. This agent intelligently combines web searches, Wikipedia knowledge, and AI reasoning to deliver high-quality research results.

## ✨ Features

- **Advanced AI Research**: Leverages Claude 3.5 Sonnet's reasoning capabilities for in-depth analysis
- **Multi-source Information**: Integrates DuckDuckGo search and Wikipedia for comprehensive data gathering
- **Structured Outputs**: Delivers research in a consistent, well-organized format
- **Automatic Documentation**: Saves research results to text files for future reference
- **Robust Error Handling**: Manages API limitations and provides graceful fallbacks

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Anthropic API key (for Claude access)

### Installation

```bash
# Clone this repository
git clone https://github.com/mandpeganesh/Python-AI-Agent-From-Scratch.git
cd Python-AI-Agent-From-Scratch

# Create and activate a virtual environment
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Set up your environment variables
```

Create a `.env` file in the project root with:

```
ANTHROPIC_API_KEY="your-anthropic-api-key"
```

## 🔍 Usage

Run the research agent:

```bash
python main.py
```

When prompted, enter your research query in natural language:

```
What are the latest developments in quantum computing?
```

### How It Works

1. The agent processes your query
2. It determines which information sources are most relevant
3. It gathers data using web searches and Wikipedia queries
4. Claude 3.5 Sonnet analyzes and synthesizes the information
5. The agent generates a structured research report
6. Results are displayed in the console and saved to a file (if requested)

## 📁 Project Structure

```
├── main.py           # Core application logic and agent initialization
├── tools.py          # Research tools implementation (search, Wikipedia, file handling)
├── requirements.txt  # Project dependencies
└── .env              # Environment variables (API keys)
```

## 📊 Research Output Format

Each research response includes:

- **Topic**: Clear definition of the research subject
- **Summary**: Comprehensive synthesis of findings
- **Key Points**: Important insights and takeaways
- **Sources**: Detailed attribution of information sources
- **Tools Used**: Transparency about which tools were employed

## 🛠️ Available Tools

| Tool | Description |
|------|-------------|
| **Web Search** | Retrieves up-to-date information from the web via DuckDuckGo |
| **Wikipedia** | Accesses structured knowledge on specific topics |
| **File Storage** | Saves research outputs for future reference |

## ⚠️ Troubleshooting

If you encounter issues with the API:

- **Rate limiting**: Implement exponential backoff retry logic
- **Timeout errors**: Consider breaking complex queries into smaller chunks
- **API overload**: Add delay between requests or use queue systems for large workloads

### Common Error Solutions

```python
# Example retry logic implementation
import time
import random

def retry_with_backoff(func, max_retries=3):
    retries = 0
    while retries < max_retries:
        try:
            return func()
        except Exception as e:
            wait_time = (2 ** retries) + random.uniform(0, 1)
            print(f"Error: {e}. Retrying in {wait_time:.2f} seconds...")
            time.sleep(wait_time)
            retries += 1
    
    # Final try
    return func()
```

## 📦 Dependencies

- `langchain`: Core framework for chaining AI components
- `langchain-anthropic`: Integration with Claude models
- `langchain-openai`: Optional OpenAI model integration
- `langchain-community`: Access to community tools
- `pydantic`: Data validation and settings management
- `python-dotenv`: Environment variable management
- `wikipedia`: Wikipedia API client
- `duckduckgo-search`: Web search capability

## 🔮 Future Enhancements

- Add support for additional research sources
- Implement PDF and academic paper analysis
- Create a web interface for easier interaction
- Add visualization tools for research results
- Support personalized research profiles

## 📄 License

[MIT License](LICENSE)

## 🙏 Acknowledgements

- Anthropic for the Claude AI model
- LangChain for the agent framework
- All contributors to the open-source libraries used