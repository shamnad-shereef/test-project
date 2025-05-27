pipeline {
    agent {
        label "primary"
    }

    environment {
        NODE_VERSION = "12.0"
    }
    stages {
        stage('setup') {
            agent {
                label "primary"
            }
            steps {
                script {
                    sh """#!/bin/bash
                        if [ ! -d venv ];then
                        source python3 -m venv venv
                        fi
                        if [ -f venv/bin/activate ];then
                        venv/bin/activate
                        fi
                        pip install -r requirements.txt
                        """
                }
            }
        }
        stage('deploy') {
            agent {
                label "primary"
            }
            steps {
                script {
                    sh """#!/bin/bash
                        if [ -f venv/bin/activate ];then
                        source venv/bin/activate
                        flask --app main run
                        fi
                        """
                }
            }
        }
    }
}
