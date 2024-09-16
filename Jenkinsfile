pipeline {
    
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        GREETING = 'HELLO JENKINS'
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

    