pipeline {
    agent {
        label 'AGENT-1'
    }
    environment{
        COURSE= "Jenkins"
    }
    
    options {
        // timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage ('Build') {
            steps{
               sh """
                 echo "$COURSE" 
                # sleep 10
                 echo "Building"
                 env


                 echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.DEPLOY}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
               """
            }
        }
        stage ('Test') {
            steps {
                sh """
                 echo "$COURSE"
                 echo "Testing"
                """
            }
        }
        stage ('Deploy') {
            steps {
                sh """
                 echo "$COURSE"
                 echo "Deploying"
                """
            }
        }

    }
    post{
        always {
            echo "I will run even pipeline fail"
            cleanWs()
        }
        success {
            echo "I will run if sucess"
        }
        failure {
            echo "I will run if failure"
        }
        aborted {
            echo "pipeline is aborted"
        }
    }
}