pipeline {
    agent { 
        label 'my-jnlp-slave'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Build Again 3"'
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