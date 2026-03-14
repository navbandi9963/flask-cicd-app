pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/navbandi9963/flask-cicd-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flaskapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f flaskapp || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flaskapp flaskapp'
            }
        }

    }
}
