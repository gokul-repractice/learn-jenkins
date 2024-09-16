pipeline {
    
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        GREETING = 'HELLO JENKINS'
    }

    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()    // It wont allow 2 builds at a time
    }

    stages {
        
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        
        stage('Deploy') {
            steps {
                sh """
                echo "Here i am writing ahell script"
                env
                sleep 10
                """
            }
        }
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    
        failure { 
            echo 'This runs when pipeline fails, used generally to send some alerts'
        }

        success { 
            echo 'I will say Hello when pipeline succeeds'
        }
    }
}

    