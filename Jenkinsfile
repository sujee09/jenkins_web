def printFromFunction() {
    println("I am printing from a function")
}

pipeline {
    
    agent any 

    options {
        timestamps()
    }

    stages {
        stage ("Build") {
            steps {
                echo "Build"
                printFromFunction()
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