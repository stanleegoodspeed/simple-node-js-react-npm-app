pipeline {
    agent { 
        label 'my-tmp-slave'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Build Again 5"'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Test"'
            }
        }
        stage('Deliver') { 
            steps {
                sh 'echo "Deliver"' 
            }
        }
    }
}