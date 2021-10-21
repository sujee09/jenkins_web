pipeline {

    agent any
    
    options {
        timestamps()
    }
    stages {
        stage ("Mr first stage") {
            steps {
                echo "This is a step in my first stage"
            }
        stage ("Print Env. Variables") {
            steps {
                sh "printenv"
            }
        }
        }
    }
}