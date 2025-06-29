# python-aws-cicd

## Project Purpose

This project demonstrates a minimal Python Flask web application deployed on AWS EC2 with a CI/CD pipeline using GitHub Actions.

---

## Running the App Locally

1. Clone the repository

2. Create and activate a virtual environment (using Python 3.8):

   python3.8 -m venv venv  
   source venv/bin/activate

3. Install dependencies:

   pip install -r requirements.txt

4. Run the app:

   python src/app.py

5. Open your browser at http://localhost:5000

---

## CI/CD Pipeline

- Pushing changes to the `main` branch triggers automatic build, test, and deployment workflows via GitHub Actions.  
- Code quality is enforced with flake8 linting.  
- Deployment targets an AWS EC2 instance via SSH.

---

## Rollback Explanation

To rollback, redeploy a previous commit by triggering the deployment workflow for that commit in GitHub Actions or manually redeploy from the EC2 instance.

---

## Repository Structure

python-aws-cicd/  
├── .github/  
│   └── workflows/  
│       ├── test.yml  
│       ├── deploy.yml  
│       └── rollback.yml (optional)  
├── docs/  
│   ├── ci-cd-pipeline.md  
│   └── deployment-strategy.md  
├── src/  
│   └── app.py  
├── tests/  
│   └── test_app.py  
├── requirements.txt  
├── README.md  
└── .gitignore  

---

## Secrets and Environments

- SSH keys and sensitive data are stored securely as GitHub repository secrets.  
- Environments are configured in GitHub for production and staging.

---

## Notes

- The Flask app uses the built-in development server and is intended for demonstration only.  
- For production use, replace with a production-grade WSGI server.  
- Ensure your AWS security groups allow traffic on the relevant ports (e.g., 5000).

---

## License

MIT License
