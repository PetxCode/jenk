pipeline{
    agent any

    stages {
        stage('buldiing'){

            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            
            steps{
                sh ''' 

                echo "start here"
                npm -v
                node -v
            '''
            }
        }
    }
}