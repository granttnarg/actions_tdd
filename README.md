# actions_tdd
A Python project demonstrating Test-Driven Development (TDD) with GitHub Actions CI/CD pipeline.
Overview
This repository showcases how to set up automated testing, code linting, and continuous integration using GitHub Actions. It implements a simple calculator with comprehensive tests and quality gates to ensure code reliability before merging.
Features

Automated Testing: Unit tests run on every pull request
Code Linting: Flake8 style checking to maintain code quality
Branch Protection: Tests and linting must pass before merging
CI/CD Pipeline: Automated workflows using GitHub Actions

Project Structure
actions_tdd/
├── calculator.py          # Main calculator implementation
├── test_calculator.py     # Unit tests
├── .github/
│   └── workflows/
│       └── main.yml       # GitHub Actions workflow
├── .flake8               # Flake8 configuration
└── README.md
Getting Started
Prerequisites

Python 3.11+
Git

Installation

Clone the repository
bashgit clone https://github.com/granttnarg/actions_tdd.git
cd actions_tdd

Create a virtual environment
bashpython -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

Install dependencies
bashpip install flake8


Running Tests Locally
Run unit tests:
`python -m unittest discover`
Run code linting:

`flake8 *.py test_*.py --max-line-length=88 --ignore=E203,W503`
Run both (recommended before pushing):

`python -m unittest discover && flake8 *.py test_*.py --max-line-length=88 --ignore=E203,W503`

GitHub Actions Workflow
The CI/CD pipeline automatically runs on:

Pull requests targeting the main branch
Pushes to the main branch

Workflow Steps

Lint Code - Checks code style with flake8
Build and Test - Runs unit tests with Python unittest

Both jobs must pass for a pull request to be mergeable.
Contributing

Create a feature branch
`git checkout -b feature/your-feature-name`

Make your changes

Write tests first (TDD approach)
Implement the feature
Ensure tests pass locally


Run quality checks
`python -m unittest discover`
`flake8 *.py test_*.py --max-line-length=88 --ignore=E203,W503`

Create a pull request

Push your branch to GitHub
Open a PR targeting main
Wait for CI checks to pass
Request review if needed

Branch Protection Rules
The main branch is protected with the following rules:

✅ Require status checks to pass before merging
✅ Require branches to be up to date before merging
✅ Require pull request reviews (optional)

Development Workflow
This project follows Test-Driven Development (TDD):

Red - Write a failing test
Green - Write minimal code to make it pass
Refactor - Clean up the code while keeping tests green

Example workflow:
# 1. Write a failing test
`python -m unittest test_calculator.TestCalculator.test_new_feature`

# 2. Implement the feature
# Edit calculator.py

# 3. Verify tests pass
`python -m unittest discover`

# 4. Check code style
`flake8 *.py test_*.py --max-line-length=88 --ignore=E203,W503`

Code Quality Standards
Line length: Maximum 88 characters
Style guide: PEP 8 (enforced by flake8)
Test coverage: Aim for comprehensive unit test coverage
Code complexity: Keep functions simple and readable
