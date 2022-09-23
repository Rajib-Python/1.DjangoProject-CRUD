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
                sh 'ssh -o StricthostKeyChecking=no prod@34.230.20.19 ; \
                sudo apt update '
            }
        }


        stage('Deploy') { 
            steps {
                sh 'echo Deploy'

          
            }
        }
    }
}
