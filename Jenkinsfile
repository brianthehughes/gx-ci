pipeline {
    agent any
    stages {
        stage('Prep & Clone') {
            steps {
                echo "Purge ./ghostbsd-build repository folder..."
                sh 'rm -rf ghostbsd-build || true'
                echo "Clone repository..."
                sh 'git clone https://github.com/brianthehughes/ghostbsd-build --depth=1 --branch=gx0a || true'
            }
        }
        stage('Run bulkbuild.sh') {
            steps {
                sh 'cd ghostbsd-build && ./bulkbuild.sh'
            }
        }
    }
}
