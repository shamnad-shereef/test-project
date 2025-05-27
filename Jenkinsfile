pipeline {
    agent any

    environment {
        NODE_VERSION = "12.0"
    }
    stages {
        stage('Build') {
            steps {
                echo ${env.NODE_VERSION}
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
