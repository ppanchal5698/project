# Project Architecture

## Overview

This is a full-stack project boilerplate designed for rapid development with Python and/or Node.js. The architecture follows a modular, maintainable structure with comprehensive tooling support.

## Directory Structure

```
project/
├── src/                    # Application source code
├── tests/                  # Test files
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions CI/CD pipeline
├── .vscode/
│   ├── settings.json       # Editor settings
│   ├── tasks.json          # Build/run tasks
│   ├── launch.json         # Debug configurations
│   └── extensions.json     # Recommended extensions
├── .ide/
│   ├── manifest.json       # File index for AI context
│   └── architecture.md     # This file
├── requirements.txt        # Python dependencies
├── package.json            # Node.js configuration
├── memory.md               # Project memory for AI assistants
└── README.md               # Project documentation
```

## Technology Stack

### Backend Options

- **Python**: FastAPI / Flask / Django
- **Node.js**: Express / NestJS / Fastify

### Frontend Options

- **React**: Next.js / Vite
- **Vue**: Nuxt 3 / Vite

### Database Options

- PostgreSQL (recommended)
- MySQL / SQLite
- Redis (caching)

### DevOps

- Docker / Docker Compose
- GitHub Actions CI/CD
- Pre-commit hooks

## Development Workflow

1. Install dependencies: `pip install -r requirements.txt` or `npm install`
2. Run development server: Use VS Code tasks or terminal commands
3. Run tests: `pytest tests/` or `npm test`
4. Lint/format: `ruff check src/` or `npm run lint`

## Design Principles

- **Modularity**: Separate concerns into distinct modules
- **Type Safety**: Use type hints (Python) or TypeScript
- **Testing**: Maintain >80% code coverage
- **Security**: Follow OWASP guidelines
- **Documentation**: Self-documenting code with docstrings
