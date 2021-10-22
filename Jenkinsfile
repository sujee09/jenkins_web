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
                sshPublisher(publishers: [sshPublisherDesc(configName: 'http', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'mv index.html /var/www/index.html', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'index.html')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }

        }
    }
}