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
                sh 'ssh -o StricthostKeyChecking=no prod@34.230.20.19"sourch /venv/bin/activate; \
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
