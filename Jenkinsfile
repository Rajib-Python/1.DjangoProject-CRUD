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
                sh 'echo Test'
            }
        }
        stage('Deploy') { 
            steps {
                sh 'ssh -o StricthostKeyChecking=no prod1@0.tcp.in.ngrok.io -p 18472; \
                cd CRUD; \
                git pull origin master; \
                pip install -r requirements.txt -- no-warn-script-location; \
                python manage.py migrate; \
                deactivate; \
                sudo systemctl restart nginx; \
                sudo systemctl restart gunicorn "'
          
            }
        }
    }
}
