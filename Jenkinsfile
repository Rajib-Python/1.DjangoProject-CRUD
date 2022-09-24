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
                sh 'ssh -o StricthostKeyChecking=no stage@stage.rajibdev.tk "source venv/bin/activate; \
                cd 1.DjangoProject-CRUD; \
                git pull origin master; \
                pip install -r requerment.txt -- no-warn-script-location; \
                python manage.py migrate; \
                deactivate; \
                sudo systemctl restart nginx; \
                sudo systemctl restart gunicorn"'

                   }
                }

        stage('Deploy to prod') { 
            input { 

                message "shell you deploy to producttion"
                ok  "yes"

            }
            steps {
                sh 'ssh -o StricthostKeyChecking=no ubuntu@prod.rajibdev.tk "source venv/bin/activate; \
                cd 1.DjangoProject-CRUD; \
                git pull origin master; \
                pip install -r requerment.txt -- no-warn-script-location; \
                python manage.py migrate; \
                deactivate; \
                sudo systemctl restart nginx; \
                sudo systemctl restart gunicorn"'



            }
        }
    }
}
