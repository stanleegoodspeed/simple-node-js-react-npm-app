pipeline {
    agent {
        docker {
            image 'docker:latest'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
				sh 'docker pull docker/compose:1.22.0'
				sh 'pip3 install docker-compose'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
