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
                bat 'javac helloworld.java'
            }
        }
        stage('Run') {
            steps {
                bat 'java helloworld'
            }
        }
       stage('Commits') {
    steps {
        script {
            def commits = bat(script: 'git log -2 --pretty=format:"%h - %s by %an"', returnStdout: true).trim()
            echo "📝 Recent Commits:\n${commits}"
        }
    }
}

    }
}
