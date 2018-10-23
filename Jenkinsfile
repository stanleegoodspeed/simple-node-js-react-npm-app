pipeline {
    agent {
        docker {
            image 'ccole3390/docker-with-compose:latest'
			args '--name docker-parent'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
				sh 'docker run -p 4000:80 hello-world && docker container ls && docker-compose --version'
				//sh 'docker exec -ti docker-dude /bin/bash docker container ls'
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
