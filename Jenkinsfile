pipeline {
    agent any
    stages {
        stage ('checkout') {
            steps {
                git 'https://github.com/Gopidesi19/first_demo_19.git'
                echo "repository successfully cloned"
            }
        }
        stage ('Build') {
            steps {
                sh 'pip install -r requirements.txt'
                echo "Build stage completed"
            }
        }
        stage ('unit tests') {
            steps {
                sh 'pytest tests/test_app.py'
                echo "Unit tests stage completed"
            }
        }
        stage ('Docker Image') {
            steps {
                sh 'docker build -t flask-app:${BUILD_NUMBER} .'
            }
        }
    }
}
