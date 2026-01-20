## Installation

### Prerequisites

Let's get everything you need to run FACT AI. This project uses modern tools that streamline development:

#### Node.js & pnpm

```bash
# Using nvm is recommended for managing Node versions (macOS/Linux)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install --lts

npm install -g pnpm@10
```

> **Windows users**: Download Node.js from [nodejs.org](https://nodejs.org/) and run `npm install -g pnpm@10.11.0`

#### Python & Poetry

```bash
# Install Python 3.11 on macOS with Homebrew
brew install python@3.11

# Install Poetry for Python dependency management
curl -sSL https://install.python-poetry.org | python3 -
```

> **Windows/Linux users**: Install Python 3.11+ from [python.org/downloads](https://www.python.org/downloads/)

#### LangGraph CLI

```bash
# Install the LangGraph command line interface
pip install "langgraph-cli[inmem]"
```

#### Verify Your Setup

Confirm everything is installed correctly:

```bash
node --version    # Should show 22 or higher
pnpm --version    # Should show 10.x
python --version  # Should show 3.11+
poetry --version  # Should show 2.1+
langgraph --version
```

### Setting Up FACT AI

Now let's get FACT AI running on your machine:

```bash
# Clone the repository
git clone https://github.com/man-in-deep/FACT-AI.git
cd FACT-AI

# Install all dependencies with a single command
pnpm setup:dev

# Launch the application
pnpm dev
```

Your FACT AI application should now be available at [http://localhost:3000](http://localhost:3000) 🚀

### API Configuration

FACT AI requires API keys for external services:

```bash
# Copy the environment template
cp .env.example .env

# Edit the file and add your API keys:
OPENAI_API_KEY=your_openai_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

Get your API keys from:
* **OpenAI**: [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
* **Tavily**: [tavily.com](https://tavily.com/) (Free tier available for testing)

### Troubleshooting Guide

If you encounter issues:

- **Poetry installation fails**: Try `pip install poetry` as an alternative
- **LangGraph CLI errors**: Ensure Python 3.11+ is installed and try `pip install --upgrade "langgraph-cli[inmem]"`
- **pnpm not found**: Restart your terminal after installation
- **Dependency conflicts**: Try `poetry env remove --all` followed by `pnpm setup:dev`
- **Port conflicts**: Ensure ports 3000 and 8000 are available on your system

## 🖥️ Running the Application

To launch the complete FACT AI system (frontend interface and backend services):

```bash
# Install all project dependencies
pnpm setup:dev

# Start the development servers
pnpm dev
```

This command will:
1. Install all Node.js packages for the web interface
2. Set up Python dependencies for the fact-checking engine
3. Launch both frontend and backend services simultaneously

Access FACT AI in your browser at http://localhost:3000

### Development Workflow

For ongoing development:

```bash
# Start only the frontend (web interface)
pnpm dev:web

# Start only the backend (fact-checking engine)
pnpm dev:agent

# Run tests
pnpm test

# Build for production
pnpm build
```

### Docker Alternative

If you prefer containerized deployment:

```bash
# Build and run with Docker Compose
docker-compose up --build

# Or with Docker directly
docker build -t fact-ai .
docker run -p 3000:3000 fact-ai
```

---

**Need help?** Check the [GitHub Issues](https://github.com/man-in-deep/FACT-AI/issues) or create a new issue with your problem details.

**Ready to verify facts?** Visit [http://localhost:3000](http://localhost:3000) after installation to start using FACT AI!