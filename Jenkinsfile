def printFromFunction() {
    println("I am printing from a function")
}

def replaceString() {
    def text = readFile file: "index.html"
    text = text.replaceAll("%BUILD_NUMBER%", "${BUILD_NUMBER}")
    writeFile file: "index.html", text: text 
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
                replaceString()
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