pipeline {
    agent {
        docker {
            image 'docker/compose:latest'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
				sh 'docker-compose up -d'
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
