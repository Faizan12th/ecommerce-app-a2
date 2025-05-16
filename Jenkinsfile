pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git(
                  url: 'https://Faizan12th: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@github.com/Faizan12th/ecommerce-app-a2.git',
                )
            }
        }

        stage('Build and Deploy with Docker') {
            steps {
                sh 'docker-compose -p ecommerce_ci -f docker-compose.ci.yml up -d --build'
            }
        }
    }
}
