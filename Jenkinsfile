pipeline {
    agent any
    stages {
        stage('Prep to Build') {
            steps {
                echo "Prep ./ghostbsd-build repository folder..."
                sh 'rm -rf ghostbsd-build || true'

                echo "Prep Jenkins/buildbsd-build working directory..."
                sh 'rm -rf /usr/jenkins/ghostbsd-build || true'

                echo "Clone experimental unstable branch..."
                sh 'git clone https://github.com/brianthehughes/ghostbsd-build --depth=1 --branch=gx0a || true'
            }
        }
        stage('KDE') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d kde -b unstable'
            }
        }
        stage('LXQT') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d lxqt -b unstable'
            }
        }
        stage('GX') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d gx -b unstable'
            }
        }
        stage('MATE') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d mate -b unstable'
            }
        }
        stage('XFCE') {
            steps {
                sh 'cd ghostbsd-build && ./build.sh -d xfce -b unstable'
            }
        }
    }
}
