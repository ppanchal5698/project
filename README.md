# Project

A full-stack project boilerplate with Python and Node.js support.

## 🚀 Quick Start

### Prerequisites

- Python 3.11+ (for Python development)
- Node.js 20+ (for JavaScript/TypeScript development)
- VS Code with recommended extensions

### Installation

**Python:**

```bash
# Create virtual environment
python -m venv .venv

# Activate virtual environment
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

**Node.js:**

```bash
npm install
```

## 📁 Project Structure

```
project/
├── src/                    # Application source code
├── tests/                  # Test files
├── .github/workflows/      # CI/CD pipelines
├── .vscode/                # VS Code configuration
├── requirements.txt        # Python dependencies
├── package.json            # Node.js configuration
└── README.md               # This file
```

## 🛠 Development

### Running the Application

**Python (FastAPI):**

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

**Node.js:**

```bash
npm run dev
```

### Running Tests

**Python:**

```bash
pytest tests/ -v --cov=src
```

**Node.js:**

```bash
npm test
```

### Linting & Formatting

**Python:**

```bash
ruff check src/ --fix
ruff format src/
mypy src/
```

**Node.js:**

```bash
npm run lint:fix
npm run format
```

## 🔧 VS Code Tasks

This project includes pre-configured VS Code tasks. Press `Ctrl+Shift+P` → "Tasks: Run Task" to see available tasks:

- **Python: Install Dependencies**
- **Python: Run Tests**
- **Python: Type Check (mypy)**
- **Python: Lint & Format (Ruff)**
- **NPM: Install Dependencies**
- **Node: Run Tests**
- **Docker: Build/Up/Down**

## 📦 Tech Stack

| Category   | Python         | Node.js         |
| ---------- | -------------- | --------------- |
| Framework  | FastAPI/Flask  | Express/Fastify |
| ORM        | SQLAlchemy 2.0 | Prisma/Drizzle  |
| Validation | Pydantic v2    | Zod             |
| Testing    | pytest         | Vitest/Jest     |
| Linting    | Ruff           | ESLint          |
| Formatting | Ruff           | Prettier        |
| Types      | mypy           | TypeScript      |

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```env
# Database
DATABASE_URL=postgresql://user:password@localhost:5432/dbname

# API Keys (replace with your values)
API_KEY=your-api-key-here

# Authentication
JWT_SECRET=your-jwt-secret-here
```

## 📚 Documentation

- [VS Code Setup Guide](VSCODE_SETUP_GUIDE.md)
- [Architecture Overview](.ide/architecture.md)

## 📄 License

MIT License - see LICENSE file for details.
