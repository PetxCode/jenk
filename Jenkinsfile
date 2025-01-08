pipeline {
    agent any

    stages {
        agent {
            docker {
                image 'node:18-alpine'
            }
        }
        stage('build') {
            steps {
                sh '''
                    node -v
                '''
            }
        }
    }
}