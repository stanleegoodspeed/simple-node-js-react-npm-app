pipeline {
    agent { 
        label 'ecs-java'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Build Again 4"'
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