pipeline {
    agent any

    stages {
        stage('Clean Previous Containers') {
            steps {
                // This forces removal of previous images/volumes/containers
                sh 'docker-compose -p ecommerce_ci -f docker-compose.yml down --rmi all --volumes --remove-orphans || true'
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
