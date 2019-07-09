pipeline {
    agent any
    stages {
        stage ('Build Servlet Project to war file') {
            steps {
                sh 'mvn clean package'
            }

            post {
                success {
                    echo 'Now archiving ....'

                    archiveArtifacts artifacts: '**/*.war'
                }                    
            }
        }
        stage('Deploy Build in staging Area'){
            steps{
               build job :'Deploy-stagingArea-Pipeline'     
            }
        }

        stage('Deploy to Production'){
            steps{
                timeout(time: 5, unit: 'Day') {
                    input message: 'Approve Production environnement ?', submitter: medali.rouissi@gmail.com
                }

                build job: 'Deploy-Production-Pipeline'
            }
            post{
                success{
                    echo 'Deployment on Production is Successful'
                }

                failure{
                    echo 'Deployment on Production failure'
                }
            }
        }
    }
}
