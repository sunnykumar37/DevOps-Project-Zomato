pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/sunnykumar37/DevOps-Project-Zomato.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t zomato-app:latest .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f zomato-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name zomato-container zomato-app:latest'
            }
        }

    }
}
