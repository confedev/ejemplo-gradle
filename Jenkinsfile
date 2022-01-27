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
                    stage("Stage Groovy"){
                        sh "echo 'Test Jenkinfile'"
                        def ejecucion = load 'gradle.groovy'
                        ejecucion.call()
                    }
                    stage("Stage Maven"){
                        sh "echo 'Test Jenkinfile'"
                        def ejecucion = load 'maven.groovy'
                        ejecucion.call()
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