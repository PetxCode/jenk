pipeline{
    agent any
    stages {
        stage('build'){
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps{
                sh '''
                    npm -v
                    npm ci
                    npm run build
                '''
            }
        }
        stage('deploy'){
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps{
                sh '''
                    npm -v
                    npm install netlify-cli -g

                    netlify -v
                '''
            }
        }
    }
}