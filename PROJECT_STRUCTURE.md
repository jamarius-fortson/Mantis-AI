# Project Structure

This document provides a detailed overview of the Mantis project structure and explains the purpose of each file and directory.

## 📂 Directory Tree

```
Mantis/
│
├── app/                                    # Main application package
│   ├── __init__.py                         # Package initialization
│   ├── main.py                             # FastAPI entrypoint & API routes
│   ├── utils.py                            # Utility functions & helpers
│   │
│   ├── agents/                             # AI Agent implementations
│   │   ├── __init__.py
│   │   └── factory.py                      # Agent factory & builder patterns
│   │
│   ├── graphs/                             # LangGraph workflow definitions
│   │   ├── __init__.py
│   │   └── orchestrator.py                 # Main orchestration graph (DAG)
│   │
│   ├── schemas/                            # Pydantic models & data structures
│   │   ├── __init__.py
│   │   └── state.py                        # State management models
│   │
│   └── tools/                              # Agent tools & integrations
│       └── __init__.py
│
├── tests/                                  # Test suite
│   ├── __init__.py                         # Test package initialization
│   ├── api_test.py                         # API endpoint tests
│   ├── test_approval_system.py             # Approval workflow tests
│   ├── test_flow.py                        # Integration flow tests
│   └── test_graph.py                       # Graph orchestration tests
│
├── index.html                              # Frontend dashboard (Glassmorphism UI)
├── run_dashboard.py                        # Dashboard server launcher
├── social_media_prompts.py                 # Social media prompt templates
│
├── requirements.txt                        # Python dependencies
├── .env.example                            # Environment variable template
├── .gitignore                              # Git ignore rules
│
├── README.md                               # Project documentation
├── CONTRIBUTING.md                         # Contribution guidelines
├── SECURITY.md                             # Security policy & guidelines
├── LICENSE                                 # MIT License
└── PROJECT_STRUCTURE.md                    # This file
```

## 📄 File Descriptions

### Application Core (`app/`)

#### `main.py`
**Purpose**: FastAPI application entry point and API route definitions

**Key Components**:
- FastAPI app initialization
- CORS middleware configuration
- RESTful API endpoints (`/health`, `/client/profile`, `/run`, `/approve`, `/reject`)
- In-memory database for brand profiles and pending approvals
- Health check endpoint

**Dependencies**:
- `fastapi`: Web framework
- `uvicorn`: ASGI server
- `pydantic`: Data validation

#### `utils.py`
**Purpose**: Utility functions and helper methods used across the application

**Contains**:
- Helper functions for data transformation
- Common utilities used by agents and workflows
- Configuration loaders

#### `agents/` Directory
**Purpose**: AI agent implementations and factory patterns

**Key Files**:
- `factory.py`: Creates and configures specialized AI agents (Trend Analyzer, Creative Engine, Safety Protocol, etc.)

#### `graphs/` Directory
**Purpose**: LangGraph workflow definitions for orchestration

**Key Files**:
- `orchestrator.py`: Main stateful DAG (Directed Acyclic Graph) that routes tasks between specialized agents

**Workflow**:
```
Client Request → Orchestrator → Trend Analyzer → Creative Engine → Safety Protocol → Data Oracle → Output
                                       ↓
                              Human Approval (if needed)
```

#### `schemas/` Directory
**Purpose**: Pydantic models for data validation and state management

**Key Files**:
- `state.py`: Defines the state structure passed through the LangGraph workflow

#### `tools/` Directory
**Purpose**: Agent tools for external integrations

**Contains**:
- Social media API connectors
- Data fetching utilities
- Content formatting tools

### Frontend (`index.html`)
**Purpose**: Interactive dashboard with glassmorphism UI design

**Features**:
- Real-time system status monitoring
- Campaign management interface
- Approval workflow UI
- Analytics and metrics display
- Terminal-style logging output

**Technologies**:
- Vanilla HTML/CSS/JavaScript
- Font Awesome icons
- Google Fonts (Inter, JetBrains Mono)
- Advanced CSS3 with glassmorphism effects

### Testing (`tests/`)

#### `api_test.py`
Tests for FastAPI endpoints including:
- Health check
- Client profile creation
- Campaign execution
- Approval/rejection workflows

#### `test_approval_system.py`
Unit tests for the human-in-the-loop approval system

#### `test_flow.py`
Integration tests for complete workflow execution

#### `test_graph.py`
Tests for LangGraph orchestration and state management

### Configuration Files

#### `requirements.txt`
Lists all Python dependencies:
- `fastapi`: Web framework
- `uvicorn`: ASGI server
- `langgraph`: Agent orchestration
- `crewai`: Multi-agent framework
- `langchain`: LLM integration
- `pydantic`: Data validation
- `python-dotenv`: Environment variable management
- `httpx`: HTTP client
- `sqlalchemy`: Database ORM
- `langchain-openai`: OpenAI integration
- `langchain-anthropic`: Anthropic integration

#### `.env.example`
Template for environment variables including:
- API keys (OpenAI, Anthropic)
- Social media credentials
- Configuration flags (MOCK_MODE)
- Port configurations

#### `.gitignore`
Specifies intentionally untracked files that Git should ignore

### Documentation

#### `README.md`
Main project documentation including:
- Project overview
- Features and architecture
- Getting started guide
- API documentation
- Contributing guidelines

#### `CONTRIBUTING.md`
Guidelines for contributing to the project including:
- Development setup
- Code standards
- Pull request process
- Commit message conventions

#### `SECURITY.md`
Security policy including:
- Vulnerability reporting process
- Security best practices
- Production deployment guidelines

#### `LICENSE`
MIT License - allows free use, modification, and distribution

## 🔄 Data Flow

1. **Client Request** → FastAPI receives request
2. **Validation** → Pydantic validates input
3. **Orchestration** → LangGraph routes to appropriate agents
4. **Processing** → Specialized agents process the task
5. **Approval** → Human approval if confidence is low
6. **Output** → Result returned to client

## 🚀 Quick Commands

| Command | Description |
|---------|-------------|
| `python -m uvicorn app.main:app --reload` | Start development server |
| `python run_dashboard.py` | Launch frontend dashboard |
| `python tests/api_test.py` | Run API tests |
| `python tests/test_flow.py` | Run integration tests |
| `python tests/test_graph.py` | Run graph tests |

## 📝 Notes

- The project uses a **multi-agent architecture** with specialized AI agents
- **LangGraph** manages state and routing through a DAG
- **Human-in-the-Loop** approval gates ensure quality control
- **MOCK_MODE** allows development without API costs
- All sensitive data should be stored in `.env` (never committed to Git)

---

For more information, see [README.md](README.md) and [CONTRIBUTING.md](CONTRIBUTING.md)
