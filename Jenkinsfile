pipeline {
    agent any

    stages {
        
        stage('build') {agent {
            docker {
                image 'node:18-alpine'
            }
            
             steps {
                sh '''
                    node -v
                    npm ci
                    npm run build

                    ls -la
                '''
            }
        }   
    }
        
        stage('deploy') {
            agent {
            docker {
                image 'node:18-alpine'
            }
            
             steps {
                sh '''
                    node -v
                    npm insall netlify-cli -g
                    netlify -v
                    
                '''
            }
        }   
    }


    }
}