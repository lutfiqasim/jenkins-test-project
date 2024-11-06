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
                echo "doing build stuff.."
                '''
            }
        }
        // Test stage
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "doing test stuff.."
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
