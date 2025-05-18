pipeline {
    agent any

    stage('Pre-Cleanup') {
    steps {
        echo 'Cleaning up old containers and volumes (if any)...'
        sh '''
            docker-compose -p $COMPOSE_PROJECT_NAME -f $COMPOSE_FILE down --volumes || true
            docker system prune -af || true
            docker volume prune -f || true
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
