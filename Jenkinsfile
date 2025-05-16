pipeline {
    agent any

    stages {
        stage('Build and Deploy with Docker') {
            steps {
                sh 'docker-compose -p ecommerce_ci -f docker-compose.ci.yml up -d --build'
            }
        }
    }
}
