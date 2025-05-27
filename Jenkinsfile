pipeline {
    agent {
        label "primary"
    }

    environment {
        NODE_VERSION = "12.0"
    }
    stages {
        stage('setup') {
            steps {
                sh """
                    if [ ! -d "venv" ];then
                        python3 -m venv venv
                    fi
                    if [ -f "venv/bin/activate ];then
                        source venv/bin/activate
                    fi
                    pip install -r requirements.txt
                    """
            }
        }
        stage('deploy') {
            steps {
                sh """
                    if [ -f "venv/bin/activate ];then
                        source venv/bin/activate
                    flask --app main run
                    fi
                    """
            }
        }
    }
}
