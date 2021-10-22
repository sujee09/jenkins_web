@Library('jenkins_shared') _

pipeline {
    
    agent any 

    options {
        timestamps()
    }

    environment {
        MYENVVAR = "testenvvar"
    }

    parameters {
        string(name: 'Name', defaultValue: 'Sujee', description: 'Your Name')
    }

    stages {
        stage ("Build") {
            steps {
                echo "Build"
                echo "${MYENVVAR}"
                echo "${name}"
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
        stage ("ArtfiactsHTML") {
            steps {
                archiveArtifacts artifacts: 'index.html', followSymlinks: false
            }
        }
        stage ("Deploy") {
            steps{
                sshPublisher(publishers: [sshPublisherDesc(configName: 'http', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'mv index.html /var/www/html/index.html', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'index.html')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }

        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'index.html', followSymlinks: false
        }
        cleanup {
            cleanWs()
        }
    }
}