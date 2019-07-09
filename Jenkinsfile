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
    }
}
