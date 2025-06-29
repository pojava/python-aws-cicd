# python-aws-cicd

## Project Purpose
This project demonstrates a minimal Python Flask web application deployed on AWS EC2 with a CI/CD pipeline using GitHub Actions.

## Running the App Locally
1. Clone the repo  
2. Create and activate a virtual environment:  
   `python3.8 -m venv venv`  
   `source venv/bin/activate`  
3. Install dependencies:  
   `pip install -r requirements.txt`  
4. Run the app with Gunicorn:  
   `gunicorn --bind 0.0.0.0:5000 src.app:app`  
5. Open your browser at `http://localhost:5000`

## Triggering CI/CD Workflows
- Push changes to the `main` branch to trigger automatic build, test, and deployment workflows via GitHub Actions.

## Rollback Explanation
- To rollback, redeploy a previous commit by triggering the deployment workflow for that commit or manually redeploy from the EC2 instance.
