pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'echo Building'
            }
        }
        stage('Test') { 
            steps {
                sh 'ssh -o StricthostKeyChecking=no prod1@0.tcp.in.ngrok.io -p 18472 ; \
                sudo apt update '
            }
        }


        stage('Deploy') { 
            steps {
                sh ''echo Deploy''

          
            }
        }
    }
}
