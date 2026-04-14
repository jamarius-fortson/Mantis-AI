# Contributing to Mantis

First off, thank you for considering contributing to Mantis! It's people like you that make this project a great tool for the community.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How Can I Contribute?](#how-can-i-contribute)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Community](#community)

## Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code. Please report unacceptable behavior to the project maintainer.

## Getting Started

### Setting up the Development Environment

1. **Fork and Clone**
   ```bash
   git clone https://github.com/YOUR_USERNAME/Enterprise-Agentic-Marketing-Engine.git
   cd Enterprise-Agentic-Marketing-Engine
   ```

2. **Create a Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up Environment Variables**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

5. **Run Tests**
   ```bash
   python api_test.py
   python test_approval_system.py
   python test_flow.py
   python test_graph.py
   ```

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues. When you are creating a bug report, please include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps which reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed after following the steps**
- **Explain which behavior you expected to see instead and why**
- **Include screenshots if applicable**
- **Include your environment details** (OS, Python version, etc.)

### ✨ Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title**
- **Provide a step-by-step description of the suggested enhancement**
- **Provide specific examples to demonstrate the enhancement**
- **Describe the current behavior and explain which behavior you expected to see instead**
- **Explain why this enhancement would be useful**

### 🔧 Your First Code Contribution

Unsure where to begin contributing? You can start by looking through these `good-first-issue` and `help-wanted` issues:

- **Good first issues**: Issues which should only require a few lines of code
- **Help wanted issues**: Issues which need community attention

## Pull Request Process

1. **Fork the repo** and create your branch from `main`
2. **Name your branch** descriptively (e.g., `feature/add-twitter-support`, `fix/dashboard-loading`)
3. **Make your changes** following the coding standards below
4. **Test your changes** thoroughly
   - Run all existing tests
   - Add new tests for new functionality
5. **Update documentation** if necessary
6. **Ensure the test suite passes** and linting checks pass
7. **Submit your pull request** with:
   - Clear title and description
   - Reference any related issues
   - List the changes you made

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
Describe how you tested your changes

## Screenshots (if applicable)
Add screenshots to help explain your changes

## Checklist
- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
```

## Coding Standards

### Python Style Guide

- Follow [PEP 8](https://pep8.org/) style guide
- Use type hints where possible
- Write docstrings for all public functions, classes, and modules
- Keep functions focused and small (single responsibility principle)
- Use meaningful variable and function names

### Code Organization

- Keep related functionality together
- Use the existing project structure as a guide
- Add new modules to appropriate directories
- Update imports following the project's import conventions

### Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

**Types:**
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Code style changes (formatting, missing semi colons, etc)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to the build process or auxiliary tools

**Example:**
```
feat(api): add rate limiting to client profile endpoint

Add rate limiting to prevent API abuse on the client profile 
creation endpoint. Uses a sliding window algorithm with 
100 requests per minute limit.

Closes #123
```

### Testing

- Write tests for all new features and bug fixes
- Follow the existing testing patterns in the project
- Ensure all tests pass before submitting PR
- Aim for high test coverage on critical paths

## Community

### Questions?

- Open an issue for bugs or feature requests
- Check existing issues and discussions
- Read the documentation thoroughly

### Maintainer

**Ismail Sajid**  
Principal AI Architect & Expert DevOps Engineer

---

Thank you for contributing! 🚀
