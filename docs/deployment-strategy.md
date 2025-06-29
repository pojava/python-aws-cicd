# Deployment Strategy

## Branching Strategy

- `main` branch: Production-ready code, triggers deployment to production EC2 instance
- `dev` branch: Development/staging environment for testing changes before production

## Environment Mapping

| Branch | Environment   | Deployment Target        |
|--------|---------------|-------------------------|
| dev    | Staging       | Staging EC2 instance    |
| main   | Production    | Production EC2 instance |

## Deployment Steps

1. Push code to `main` branch
2. GitHub Actions `deploy.yml` workflow builds, tests, and deploys to EC2
3. EC2 instance runs Gunicorn server to serve the Flask app

## Rollback Instructions

- Use the manual rollback workflow (`rollback.yml`) from GitHub Actions to deploy a previous commit/tag by specifying the version input
- Alternatively, SSH into the EC2 instance, checkout previous commit, and restart the app service manually
