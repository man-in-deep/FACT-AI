# FACT-AI
Hey everyone! I'm excited to introduce **FACT AI** - a fact-checking system I've been developing. This is a comprehensive LangGraph implementation that verifies the factual accuracy of text by breaking it down into individual claims, checking each one against real-world evidence, and generating detailed accuracy reports.

**FACT AI**

The system is structured into three modular components for optimal performance:

**Claim Extractor (claim_extractor/)** - Extracts factual claims from text using the Claimify methodology  
**Claim Verifier (claim_verifier/)** - Validates each claim through Tavily Search evidence  
**Fact Checker (fact_checker/)** - Orchestrates the complete workflow and produces final reports

## 🎯 Why I Built This
LLM-generated content (and human writing) often contains factual inaccuracies. I created FACT AI to systematically identify which statements are reliable and which require verification.

## 🔄 How It Works
1. **Input** - Provide any text you want to fact-check (questions with answers, articles, etc.)
2. **Claim Extraction** - The system decomposes text into testable claims, handling pronouns, context, and ambiguity
3. **Claim Verification** - Each claim is researched using web searches, with evidence analyzed for support, refutation, or inconclusive status
4. **Report Generation** - Receive a comprehensive analysis showing exactly which claims are substantiated

## 🏗️ System Architecture
Built on LangGraph for workflow orchestration:
For deeper technical understanding, explore the component READMEs:
- **[Claim Extractor README](https://github.com/man-in-deep/FACT-AI/tree/main/claim_extractor)** - Claim extraction methodology
- **[Claim Verifier README](https://github.com/man-in-deep/FACT-AI/tree/main/claim_verifier)** - Evidence verification process
- **[Fact Checker README](https://github.com/man-in-deep/FACT-AI/tree/main/fact_checker)** - System orchestration

## ⚙️ Customization
Each component includes configurable settings in their respective `config/` directories:
- LLM temperature controls (creativity vs. determinism)
- Web search result quantities
- Retry mechanisms for ambiguous claims
- And more...

## 📚 Research Foundation
The **claim_extractor** implements the Claimify methodology from Metropolitansky & Larson's 2025 paper, addressing ambiguity in claim extraction.

The **claim_verifier** draws inspiration from the Search-Augmented Factuality Evaluator (SAFE) approach in Wei et al.'s 2024 work on long-form factuality.

## ⚠️ Implementation Notes
While grounded in academic research, this implementation includes practical enhancements:
- Voting mechanisms for disambiguation
- Multi-retry verification strategies
- Real-world optimization for production use

## 🚀 Quick Start
```bash
git clone https://github.com/man-in-deep/FACT-AI.git
cd FACT-AI
pnpm setup:dev
pnpm dev
```

## 📂 Project Structure
```
FACT-AI/
├── .langgraph_api/           # LangGraph configuration
├── apps/
│   ├── agent/                # Core fact-checking modules
│   │   ├── claim_extractor/  # Claim extraction
│   │   ├── claim_verifier/   # Claim verification
│   │   ├── fact_checker/     # System orchestration
│   │   └── utils/            # Shared utilities
│   └── web/                  # Web interface (React/Next.js)
├── packages/                 # Shared packages
└── scripts/                  # Utility scripts
```

## 🙏 Acknowledgments
This project builds upon significant work from:
- **Dasha Metropolitansky & Jonathan Larson** (Microsoft Research) - Claimify methodology
- **Jerry Wei et al.** (Google DeepMind) - SAFE evidence retrieval concepts
- **LangChain team** - LangGraph workflow orchestration
- **OpenAI** - LLM capabilities
- **Tavily AI** - Search API integration

## 🛣️ Roadmap
- **Evaluation Agent** - Performance assessment and reliability metrics
- **Public API Service** - Cloud-based fact-checking API
- **Additional Evidence Sources** - Expand beyond web search

## 📝 Contributing
Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Submit a Pull Request

Ensure your code follows existing conventions and includes appropriate documentation updates.

## 📄 License
MIT License - See [LICENSE](https://github.com/man-in-deep/FACT-AI/blob/main/LICENSE) for details.

---

**Check out the project:** [https://github.com/man-in-deep/FACT-AI](https://github.com/man-in-deep/FACT-AI)  
**Experience FACT AI** - Because accuracy matters!
