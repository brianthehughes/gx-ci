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
        stage('Build LXQT Unstable') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d lxqt -b unstable'
            }
        }
        stage('Build GX Unstable') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d gx -b unstable'
            }
        }
    }
}
