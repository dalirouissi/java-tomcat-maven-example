pipeline {
    agent any
    stages {
        stage ('Initializing') {
            steps {
                sh ''' 
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build'){
            steps{

               echo 'Hello World'     

            }
        }
        stage ('DEPLOY'){
            steps{
               echo 'DEPLOY ARTIFACT TEST CASE ...'     
            }
        }
    }
}
