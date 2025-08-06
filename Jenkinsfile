pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'javac helloworld.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java helloworld'
            }
        }
        stage('Commits') {
            steps {
                script {
                    def commits = sh(script: "git log -2 --pretty=format:'%h - %s by %an'", returnStdout: true).trim()
                    echo "📝 Recent Commits:\n${commits}"
                }
            }
        }
    }
}
