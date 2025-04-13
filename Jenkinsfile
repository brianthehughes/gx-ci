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
                echo "Purge ./ghostbsd-build repository folder..."
                sh 'rm -rf ghostbsd-build || true'
            }
        }
        stage('Stage 3 - Git Clone') {
            steps {
                echo "Clone repository..."
                sh 'git clone https://github.com/brianthehughes/ghostbsd-build --depth=1 --branch=gx0a || true'
            }
        }
        stage('Stage 4 - Bulk Buld per bulkbuild.sh') {
            steps {
                sh 'cd ghostbsd-build && ./bulkbuild.sh'
            }
        }
    }
}
