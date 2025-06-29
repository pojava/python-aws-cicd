# Deployment Strategy Documentation

## Branching Strategy

- **main**: Production-ready code; triggers deployment workflow.
- **dev**: Staging environment for testing before merging to main.

## Environment Mapping

| Branch | Environment  | Description              |
|--------|--------------|--------------------------|
| main   | Production   | Live deployment on EC2   |
| dev    | Staging      | Test environment          |

## Deployment Steps

1. Developer pushes code to `dev` branch for staging testing.
2. Once approved, code is merged into `main`.
3. The `deploy.yml` workflow triggers deployment to EC2.
4. The app runs on EC2 accessible via public IP.

## Rollback Instructions

- Use the **rollback.yml** workflow from GitHub Actions.
- Manually trigger rollback with a version input (commit SHA or tag).
- The workflow deploys the selected version and restarts the app on EC2.
- Alternatively, redeploy previous versions manually via SSH.

---

**Important:** The app runs on a development Flask server for demo purposes only. For production, use a WSGI server like Gunicorn behind Nginx.
