pipeline {
    agent {
        node {
            label 'docker-agent-python'
        }
    }
    //   Trigger pipeline every minute
    triggers {
        pollSCM '* * * * *'
    }
    //   Three stages pipeline
    stages {
        // Build stage
        stage('Build') {
            steps {
                echo 'Building..'
                sh '''
            cd myapp
            # Create a virtual environment since it didn't allow to install packages globally in Jenkins
            python3 -m venv venv

            # Activate the virtual environment
            . venv/bin/activate

            # Upgrade pip to ensure it's the latest version
            pip install --upgrade pip

            # Install dependencies from requirements.txt
            pip install -r requirements.txt
        '''
            }
        }
        // Test stage
        stage('Test') {
            steps {
                echo 'Testing..'
                sh '''
                cd myapp
                # use virtual environment
                . venv/bin/activate
                python3 hello.py
                python3 hello.py --name=Lutfi
                '''
            }
        }
        // Deliver stage
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
