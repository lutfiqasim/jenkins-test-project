pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    //   Trigger pipeline every minute
      triggers {
        pollSCM('* * * *')
      }
    //   Three stages pipeline
    stages {
        // Build stage
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        // Test stage
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
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
