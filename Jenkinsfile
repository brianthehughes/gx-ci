pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!" || true'
                }
        }
        stage('List') {
            steps {
                sh 'cd /usr/local' || true'
                sh 'ls -lah ||  true'
                sh 'echo "Hey"
            }
        }
    }
}
