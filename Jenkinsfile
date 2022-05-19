pipeline {
     agent any
     stages {
         stage('clean up') {
            steps{
                sh(script: """
                    ls
                    echo "clean up"
                    pwd
                    rm -rf *
                """)
                }
        }
         stage('Checkout') {
             steps{
                echo "Checkout"
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'david-github-token', url: 'https://github.com/davidxy123/fair-play.git']]])
                sh "ls -lrt"
                  }
         }
        stage('Check files with tree view') {
            steps{
                sh(script: """
                   echo "tree view"
                   sh "tree -lh"
                """)
            }
        }
    }
}
