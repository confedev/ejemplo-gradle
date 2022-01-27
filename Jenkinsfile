pipeline {
    agent any
    environment {
        NEXUS_USER         = credentials('token-nexus-curl-useradmin')
        NEXUS_PASSWORD     = credentials('token-nexus-curl-passadmin')
    }
    stages {
        stage("Pipeline"){
            steps {
                script{
                    stage("Test Jenkinfile"){
                        sh "echo 'Test Jenkinfile'"
                        // code
                    }
                }
            }
            post {
                always {
                    sh "echo 'fase always executed post'"
                }
                success {
                    sh "echo 'fase success'"
                }
                failure {
                    sh "echo 'fase failure'"
                }
            }
        }
    }
}