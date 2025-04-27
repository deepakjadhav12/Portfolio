pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/deepakjadhav12/Portfolio.git'
            }
        }

        stage('Docker Compose Up') {
            steps {
                script {
                    bat '''
                    docker-compose down || exit 0
                    docker-compose up --build -d
                    '''
                }
            }
        }
    }

    post {
        success {
            echo '✅ Portfolio Website Deployed Successfully with Docker Compose!'
        }
        failure {
            echo '❌ Deployment Failed. Please check console logs.'
        }
    }
}
