pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/ashtarali4/Taskflow.git'
            }
        }
        stage('Deploy Pipeline Test Environment') {
            steps {
                sh 'sudo docker compose -f docker-compose.ci.yml down || true'
                sh 'sudo docker compose -f docker-compose.ci.yml up -d'
            }
        }
    }
}
