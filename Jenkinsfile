pipeline {
    agent any

    stages {
        stage('Clean Existing Containers') {
            steps {
                echo 'Stopping and removing existing ecommerce_ci containers...'
                sh '''
                    docker stop ecommerce_ci_backend ecommerce_ci_frontend || true
                    docker rm ecommerce_ci_backend ecommerce_ci_frontend || true
                '''
            }
        }


    stages {
        stage('Build and Deploy with Docker') {
            steps {
                sh 'docker-compose -p ecommerce_ci -f docker-compose.yml up -d --build'
            }
        }
    }
}
