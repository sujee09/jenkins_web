@Library('jenkins_shared') _

pipeline {
    
    agent any 

    options {
        timestamps()
    }

    stages {
        stage ("Build") {
            steps {
                echo "Build"
                helloVariable("Sujee")
                script {
                    utils.replaceString()
                }
            }

        }
        stage ("Test") {
            steps {
                sh "bash ./testBuild.sh"
              
            }

        }
        stage ("Deploy") {
            steps{
                echo "Deploy"
            }

        }
    }
}