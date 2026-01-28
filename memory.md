# Project Memory

## Architecture Overview

This is a full-stack project boilerplate with support for both Python and Node.js development. The project uses a modular architecture with clear separation between source code (`src/`) and tests (`tests/`). The development environment is configured with comprehensive VS Code settings, tasks, and debug configurations.

## Module Responsibilities

- **src/**: Main source code directory for application logic
- **tests/**: Unit and integration tests
- **.github/**: GitHub workflows for CI/CD automation
- **.vscode/**: VS Code workspace configuration (settings, tasks, debug, extensions)
- **.ide/**: IDE context management for AI assistants

## API Endpoints

_No endpoints defined yet - add your API routes here_

## Database Schema

_No schema defined yet - add your database models here_

## Recent Changes

### 2026-01-28T00:00:00Z - Initial project scaffold

- CREATED: Project structure with Python + Node.js support
- CREATED: VS Code configuration (settings.json, tasks.json, launch.json)
- CREATED: GitHub Actions CI workflow
- CREATED: IDE context management (.ide/)
- Commit-style: chore: initialize project with full-stack boilerplate

## Open Questions / TODOs

- [ ] Add application-specific source code in `src/`
- [ ] Add unit tests in `tests/`
- [ ] Configure environment variables in `.env`
- [ ] Set up database connections if needed
- [ ] Add API endpoints and routes

## Secrets Reference

- ENV:DATABASE_URL (if using database)
- ENV:API_KEY (if using external APIs)
- ENV:JWT_SECRET (if using authentication)
