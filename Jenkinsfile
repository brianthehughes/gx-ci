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
        stage('build LXQT') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d lxqt -b unstable'
            }
        }
        stage('build GX') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d gx -b unstable'
            }
        }
        stage('build MATE') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d mate -b unstable'
            }
        }
        stage('build XFCE') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d xfce -b unstable'
            }
        }
    }
}
