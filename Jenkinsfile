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
            '''
            }
        }
    }
}