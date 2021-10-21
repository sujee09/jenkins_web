pipeline {
    
    agent any 

    stages {
        stage ("Build") {
            steps {
                echo "Build"
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