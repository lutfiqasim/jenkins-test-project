pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    //   Triggers pipeline every 5 minutes if there is a change in the repository
      triggers {
        pollSCM('H/5 * * * *')
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
