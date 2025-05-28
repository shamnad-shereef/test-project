pipeline {
    agent {
        label "primary"
    }

    environment {
        NODE_VERSION = "12.0"
    }
    triggers {
        githubPullRequests events: [], spec: '* * * * *', triggerMode: 'CRON'
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
                        python3 -m venv venv
                        fi
                        if [ -f venv/bin/activate ];then
                        source venv/bin/activate
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
                        tmux new -d -s 'flask --app main run'
                        fi
                        whoami
                        ls
                        """
                }
            }
        }
    }
}
