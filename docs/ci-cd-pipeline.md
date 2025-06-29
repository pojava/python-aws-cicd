# CI/CD Pipeline Documentation

## Workflow Files

- `test.yml`: Runs tests and linting on each push/pull request
- `deploy.yml`: Deploys the app to EC2 on push to `main`
- `rollback.yml` (optional): Manual rollback to a previous commit or tag via workflow dispatch

## Triggers

- `test.yml`: on push and pull_request on branches `dev` and `main`
- `deploy.yml`: on push to `main`
- `rollback.yml`: manual trigger with input for version to rollback to

## Secrets Used

- `EC2_HOST`: EC2 public DNS or IP
- `EC2_USER`: SSH user (e.g., ec2-user)
- `EC2_SSH_KEY`: Private key for SSH access

## Dependency Setup

- Python 3.8 environment created on EC2
- Dependencies installed from `requirements.txt`
- Gunicorn used as the production server

## Directory Structure

