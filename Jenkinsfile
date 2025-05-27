pipeline {
    agent {
        label "primary"
    }

    environment {
        NODE_VERSION = "12.0"
    }
    stages {
        stage('Build') {
            steps {
                sh "ls"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
