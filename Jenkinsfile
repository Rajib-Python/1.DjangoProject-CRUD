pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'echo  Building'
            }
        }
        stage('Test') { 
            steps {
                sh ' echo Hello'
            }
        }


        stage('Deploy to stageing') { 
            steps {
                sh 'ssh -o StricthostKeyChecking=no prod1@0.tcp.in.ngrok.io -p 18472 "source venv/bin/activate; \
                cd 1.DjangoProject-CRUD; \
                git pull origin master; \
                pip install -r requerment.txt -- no-warn-script-location; \
                python manage.py migrate; \
                deactivate; \ "'
          
            }
        }
    }
}
