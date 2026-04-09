pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/jamesarochristober/jenkins-pipeline-demo.git'
            }
        }

        stage('Setup Python') {
            steps {
                sh 'python3 -m venv venv'
                sh 'source venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                sh 'source venv/bin/activate && nohup python app.py &'
            }
        }
    }
}

