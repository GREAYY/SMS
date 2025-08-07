pipeline {
    agent any
    stages {
        stage('Setup Python') {
            steps {
                sh '''
                  python3 -m venv venv
                  . venv/bin/activate
                  pip install -r requirements.txt
                '''
            }
        }
        stage('Run script') {
            steps {
                sh '. venv/bin/activate && python script.py'
            }
        }
    }
}
