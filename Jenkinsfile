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
                sh 'ls -lah'
            }
        }
    }
}
