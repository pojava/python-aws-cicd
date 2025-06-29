# CI/CD Pipeline Documentation

## Purpose

This pipeline automates testing, linting, deployment, and rollback of the Python Flask app to an AWS EC2 instance.

## Workflow Files

- **test.yml**: Runs linting (flake8) and unit tests (pytest) on each push and pull request.
- **deploy.yml**: Deploys the app to EC2 on successful merge to `main`.
- **rollback.yml** (optional): Manually triggered rollback to a previous commit or tag.

## Triggers

- `test.yml`: triggers on `push` and `pull_request`.
- `deploy.yml`: triggers on push to `main`.
- `rollback.yml`: triggers manually via workflow_dispatch input.

## Secrets Used

- `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`: AWS credentials for deployment.
- `EC2_HOST`, `EC2_USER`, `EC2_SSH_KEY`: SSH connection info for EC2 deployment.

## Dependency Setup

- Python 3.8 virtual environment is created.
- Dependencies installed from `requirements.txt`.
- Code quality checks use flake8.
- Testing uses pytest.

## Directory Structure

python-aws-cicd/
├── docs/
│ ├── ci-cd-pipeline.md
│ └── deployment-strategy.md
├── src/
│ └── app.py
├── tests/
│ └── test_app.py
├── requirements.txt
├── .github/
│ └── workflows/
│ ├── test.yml
│ ├── deploy.yml
│ └── rollback.yml
├── venv/
└── README.md
