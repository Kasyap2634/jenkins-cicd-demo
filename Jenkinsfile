pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh 'docker run --rm -v "$PWD":/app -w /app python:3.12-slim sh -c "pip install -r requirements.txt && pytest"'
      }
    }
    stage('Build') {
      steps {
        sh 'docker build -t demo-app:${BUILD_NUMBER} .'
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker rm -f demo-app || true'
        sh 'docker run -d --name demo-app -p 5000:5000 demo-app:${BUILD_NUMBER}'
      }
    }
  }
}
