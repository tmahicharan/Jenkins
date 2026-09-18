pipeline {
    agent {
        label 'AGENT-1'
    }
    environment{
        COURSE= "Jenkins"
    }
    options {
        timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuilds()
    }
    stages {
        stage ('Build') {
            steps{
               sh """
                 echo "$COURSE" 
                 sleep 10
                 echo "Building"
                 env
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