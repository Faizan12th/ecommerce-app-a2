pipeline {
    agent any

    stages {
        stage('Stop and Remove Old Manual Containers') {
            steps {
                echo 'Stopping and removing old manual containers if they exist...'

                // Stop and remove ecommerce-app-a2_frontend_1
                sh 'docker stop ecommerce-app-a2_frontend_1 || true'
                sh 'docker rm ecommerce-app-a2_frontend_1 || true'

                // Stop and remove ecommerce-app-a2_backend_1
                sh 'docker stop ecommerce-app-a2_backend_1 || true'
                sh 'docker rm ecommerce-app-a2_backend_1 || true'
            }
        }

        stage('Build and Deploy with Docker') {
            steps {
                echo 'Building and deploying Docker containers for ecommerce_ci project...'
                sh 'docker-compose -p ecommerce_ci -f docker-compose.yml up -d --build'
            }
        }
    }
}

