pipeline {
    agent any
    stages {
        stage('Stage 1') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                }
        }
        stage('Stage 2 - Cleaning') {
            steps {
                echo "Purge ghostbsd-build folder..."
                sh 'cd /storage/jenkins && rm -rf ghostbsd-build || true'
            }
        }
        stage('Stage 3 - Git Clone') {
            steps {
                sh 'git clone https://github.com/brianthehughes/ghostbsd-build --depth=1 --branch=gx0a || true'
            }
        }
        stage('Stage 4 - Single Build - GX Unstable') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d gx -b unstable'
            }
        }
    }
}
