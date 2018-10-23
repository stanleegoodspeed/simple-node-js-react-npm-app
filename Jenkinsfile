pipeline {
    agent {
        docker {
            image 'docker:latest'
			args '--name docker-dude'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
				sh 'docker run -p 4000:80 --name hello-world hello-world && docker container ls'
				sh 'docker exec -ti docker-dude /bin/bash docker container ls'
				//sh 'docker exec -ti hello-world /bin/bash "echo COLIN"'
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
