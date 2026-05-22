# ResearchAgent 🔬

A sophisticated **multi-agent AI research system** that automates end-to-end research workflows. Four specialized AI agents collaborate seamlessly to search the web, scrape content, write comprehensive reports, and provide critical feedback.

## Features ✨

- **🔍 Search Agent** - Queries the web using Tavily API to gather recent, reliable information
- **📄 Reader Agent** - Intelligently scrapes and extracts clean content from URLs using multiple extraction strategies
- **✍️ Writer Chain** - Synthesizes research findings into structured, professional reports
- **🧐 Critic Chain** - Reviews reports with detailed feedback, scoring, and improvement suggestions
- **🎨 Beautiful UI** - Modern Streamlit web interface with glassmorphic design and real-time pipeline visualization
- **⬇️ Export Ready** - Download research reports as markdown files

## Tech Stack 🛠️

- **LangChain** - Multi-agent orchestration and LLM chaining
- **Groq AI** - Fast LLM inference (Qwen3-32B model)
- **Tavily** - Web search API for reliable information gathering
- **Streamlit** - Interactive web UI
- **BeautifulSoup4 & Trafilatura** - HTML parsing and content extraction
- **python-dotenv** - Environment configuration

## Installation 📦

1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd research-agent
   ```

2. **Create and activate virtual environment**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file in the project root:
   ```
   TAVILY_API_KEY=your_tavily_api_key
   GROQ_API_KEY=your_groq_api_key
   ```

## Usage 🚀

### Web Interface (Recommended)
```bash
streamlit run app.py
```
This launches an interactive web interface where you can:
- Enter any research topic
- Watch the pipeline execute in real-time
- View search results, scraped content, and final report
- Get AI-powered feedback on the research quality
- Download the report as markdown

### Command Line
```bash
python main.py
```
Edit the `topic` variable in `main.py` to research different subjects.

## Project Structure 📁

```
research-agent/
├── app.py                          # Streamlit web interface
├── main.py                         # CLI entry point
├── requirements.txt                # Python dependencies
├── src/
│   ├── agents/
│   │   └── agents.py              # Agent and chain definitions
│   ├── tools/
│   │   └── tools.py               # Web search and scraping tools
│   └── pipeline/
│       └── pipeline.py            # Main research pipeline orchestration
└── README.md
```

## How It Works 🔄

### Pipeline Flow

1. **Search Phase** - Search agent queries the web for relevant information
2. **Scraping Phase** - Reader agent picks the most relevant URL and extracts deep content
3. **Writing Phase** - Writer chain synthesizes findings into a structured report
4. **Critique Phase** - Critic chain evaluates the report and provides feedback

Each phase builds on the previous one, creating a comprehensive research workflow.

## Key Components 🔑

### Agents
- **Search Agent** - Uses Tavily API to find top 5 relevant results with titles, URLs, and snippets
- **Scraping Agent** - Employs multiple extraction strategies (trafilatura → readability → fallback) for robust content extraction

### Chains
- **Writer Chain** - Generates professional reports with introduction, key findings, conclusion, and sources
- **Critic Chain** - Provides scoring (X/10), strengths, improvement areas, and verdict

### Tools
- `web_search(query)` - Searches for information across the internet
- `scrape_url(url)` - Extracts readable content from web pages

## Configuration 🔧

### LLM Settings
The system uses Groq's fast inference with Qwen3-32B model. To change the model:
1. Edit `src/agents/agents.py`
2. Modify the `ChatGroq` instantiation with different model name

### API Keys
Both Tavily and Groq API keys are required:
- **Tavily** - https://tavily.com
- **Groq** - https://console.groq.com

## Example Use Cases 📚

- "Roadmap for AGI development in next 5 years"
- "Future of LLM in Tech Industry"
- "Latest AI Agents released in 2026"
- Any research topic imaginable!

## Customization 🎨

### Modify Agent Behaviors
Edit prompts in `src/agents/agents.py` to customize:
- Search depth and result count
- Report structure and content
- Feedback criteria and scoring

### Add New Tools
Extend the system by adding new tools to `src/tools/tools.py` and integrating them into the agents.

