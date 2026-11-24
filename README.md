# Automated CI/CD Pipeline with Jenkins and AWS EC2

Every push to GitHub automatically tests, builds and deploys a Flask app.

## Architecture
GitHub → Webhook → Jenkins (EC2) → Docker → Live app

## Tech used
AWS EC2, Jenkins, Docker, GitHub, Python (Flask), pytest

## How it works
1. I push code to GitHub
2. A webhook notifies Jenkins
3. Jenkins runs tests, builds a Docker image, deploys the container

## Setup steps
1. Launch an Ubuntu EC2 instance, open ports 22, 8080, 5000
2. Install Java 21, Jenkins and Docker
3. Create a Pipeline job using the Jenkinsfile in this repo
4. Add the GitHub webhook

## Screenshots


![Pipeline](screenshots/pipeline.png)




![App](screenshots/app.png)



## Problems I solved
- Jenkins needed Java 21, not 17
- Node went offline due to a low temp space threshold
- Jenkinsfile was in a subfolder, so Jenkins couldn't find it
