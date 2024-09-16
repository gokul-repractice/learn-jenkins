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
        disableConcurrentBuilds()    // It wont allow multiple builds at a time. allows one by one only
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                #sleep 10
                """
            }
        }

        stage('check Params') {
            steps {
                sh """
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
                """
            }
        }
    }
 
    // Post Build
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

    