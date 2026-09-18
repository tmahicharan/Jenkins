pipeline {
    environment{
        COURSE= "Jenkins"
    }
    agent {
        label 'AGENT-1'
    }
    stages {
        stage ('Build') {
            steps{
               sh """
                 echo "$COURSE" 
                 echo "Building"
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
        always{
            echo "I will run even pipeline fail"
            cleanWS()
        }
        success{
            echo "I will run if sucess"
        }
        failure{
            echo "I will run if failure"
        }
    }
}