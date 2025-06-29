# CI/CD Pipeline Documentation

## Workflow File Purpose

- **test.yml**: Runs unit tests and code quality checks (flake8) on every push and pull request.
- **deploy.yml**: Deploys the application to AWS (e.g., EC2) on successful pushes to the `main` branch.
- **rollback.yml** (optional): Allows manual rollback to a previous deployment version.

## Trigger Descriptions

- `test.yml`: triggered on `push` and `pull_request` events.
- `deploy.yml`: triggered on `push` events to the `main` branch.
- `rollback.yml`: triggered manually via `workflow_dispatch` with a version input.

## Secrets Used

- `AWS_ACCESS_KEY_ID`: AWS access key for deployment.
- `AWS_SECRET_ACCESS_KEY`: AWS secret key for deployment.
- (Add any other secrets like SSH keys if used.)

## Dependency Setup

- Python 3.8 is used.
- Virtual environment is created in the workflow.
- Required Python packages installed via `pip install -r requirements.txt`.
- Code quality tools like `flake8` are installed and run as part of tests.

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
├── test.yml
├── deploy.yml
└── rollback.yml (optional)
