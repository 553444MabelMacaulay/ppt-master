# PPT Master

A powerful AI-powered presentation generator that creates professional PowerPoint files from text prompts.

> Fork of [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) with additional features and improvements.

## Features

- 🤖 AI-driven slide content generation using LLMs
- 📊 Multiple presentation themes and layouts
- 📝 Markdown-to-PPTX conversion
- 🌐 Web interface for easy interaction
- 🔌 REST API for programmatic access
- 📤 Export to `.pptx` format

## Prerequisites

- Python 3.10+
- An OpenAI-compatible API key (see `.env.example`)

## Installation

```bash
# Clone the repository
git clone https://github.com/your-username/ppt-master.git
cd ppt-master

# Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy and configure environment variables
cp .env.example .env
# Edit .env with your API keys and settings
```

## Configuration

Copy `.env.example` to `.env` and fill in the required values:

| Variable | Description | Required |
|---|---|---|
| `OPENAI_API_KEY` | Your OpenAI (or compatible) API key | ✅ |
| `OPENAI_BASE_URL` | Custom API base URL (for local models) | ❌ |
| `MODEL_NAME` | LLM model to use (default: `gpt-4o`) | ❌ |
| `MAX_SLIDES` | Maximum number of slides to generate | ❌ |

See `.env.example` for the full list of options.

## Usage

### Web Interface

```bash
python app.py
```

Open your browser at `http://localhost:7860`.

### CLI

```bash
python main.py --topic "Introduction to Machine Learning" --slides 10 --output output.pptx
```

### API

```bash
curl -X POST http://localhost:7860/api/generate \
  -H "Content-Type: application/json" \
  -d '{"topic": "Quantum Computing Basics", "num_slides": 8}'
```

## Project Structure

```
ppt-master/
├── app.py              # Gradio web application entry point
├── main.py             # CLI entry point
├── core/
│   ├── generator.py    # LLM-based content generation
│   ├── builder.py      # PPTX file construction
│   └── templates/      # Slide templates and themes
├── utils/
│   ├── config.py       # Configuration loader
│   └── helpers.py      # Utility functions
├── requirements.txt
├── .env.example
└── README.md
```

## Contributing

Contributions are welcome! Please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feat/amazing-feature`)
3. Commit your changes following [Conventional Commits](https://www.conventionalcommits.org/)
4. Push to the branch and open a Pull Request

See [AGENTS.md](AGENTS.md) for AI agent contribution guidelines.

## License

MIT License — see [LICENSE](LICENSE) for details.
