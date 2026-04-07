pipeline {
    agent {
        docker {
            image 'python:3.9'
        }
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/sarthak24shirbhate/Deloitte.git',
                    credentialsId: 'github-creds'
            }
        }

        stage('Install') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run App (Test)') {
            steps {
                sh 'python app.py & sleep 5'
            }
        }

    }
}
