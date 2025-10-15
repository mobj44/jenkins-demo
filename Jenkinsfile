pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run tests') {
            steps {
                sh 'pytest -v'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application... (pretend step)'
            }
        }
    }
}
