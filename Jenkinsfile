pipeline{
    agent any
    environment {
        NETLIFY_SITE_ID = "0b93fbfb-c27b-4de6-adb8-a048b83880b7"
        NETLIFY_AUTH_TOKEN = credentials('netlify-token')
    }
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
                    npm install netlify-cli
                    node_modules/.bin/netlify -v
                    echo "Running to production siteID: $NETLIFY_SITE_ID"
                    node_modules/.bin/netlify status
                    
                    node_modules/.bin/netlify deploy --dir=dist --prod
                '''
            }
        }
    }
}