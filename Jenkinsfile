pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps { checkout scm }
    }
    stage('Test (Python in Docker)') {
      steps {
        script {
          docker.image('python:3.11').inside {
            sh '''
              python -V
              python -m pip install --upgrade pip
              python -m pip install -r requirements.txt
              pytest -v
            '''
          }
        }
      }
    }
    stage('Deploy') {
      steps { echo 'Deploying… (demo stub)' }
    }
  }
  post {
    always { archiveArtifacts artifacts: '**/pytest*.xml', allowEmptyArchive: true }
  }
}
