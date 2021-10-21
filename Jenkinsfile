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
                    utils.printFromFunction()
                }
            }

        }
        stage ("Test") {
            parallel {
                stage ("Test on Windows") {
                    steps {
                        echo "Windows"
                    }
                }
                stage ("Test on Linux"){
                    steps {
                        echo "Linux"
                    }
                }
            }

        }
        stage ("Deploy") {
            steps{
                echo "Deploy"
            }

        }
    }
}