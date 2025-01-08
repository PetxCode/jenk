pipeline{
    agent any

    stages {
        stage('buldiing'){

            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            
            steps{
                sh ''' 

                echo "start here"
                npm -v
                node -v

                npm ci
                npm run build

                ls -la
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

                echo "start deploy here with Netlify"
                npm install netlify-cli -g

                netlify --version

            '''
            }
        }
    }
}