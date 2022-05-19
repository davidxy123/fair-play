pipeline {
     agent any
     stages {
         stage('clean up') {
            steps{
                sh(script: """
                    echo "clean up"
                    pwd
                    rm -rf *
                    mvn --version
                """)
                }
        }
        stage('test pipeline') {
            steps{
                sh(script: """
                   echo "hello"
                   export ALL_PROXY=socks5://127.0.0.1:10686/ 
                   git clone https://github.com/davidxy123/fair-play.git
                   cd ./fair-play
                   ls
                   whoami
                   id
                   docker ps -a
                   docker images -a
                """)
            }
        }
    }
}
