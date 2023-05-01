pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'pip install pylint' 
                sh 'pylint *.py' 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'cp . /deploy' 
                sh 'python manage.py migrate'
                sh 'source venv/bin/activate' 
                sh 'python3 manage.py runserver' 
            }
        }
    }
}
