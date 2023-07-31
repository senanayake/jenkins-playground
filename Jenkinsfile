pipeline {
    agent any
    stages {
        stage("This is the verybest jenkins playground stage 1") {
            steps {
                script {
                    def currentUser = sh(returnStdout: true, script: 'whoami').trim()
                    echo "Current user: ${currentUser}"
                }
                sh '''
                    env | grep -e PATH -e JAVA_HOME
                    which java
                    java -version
                '''
                
            }
        }
        stage("Stage 2") {
            steps {
                echo "This is stage 2"
            }
        }
        stage("Stage 3") {
            steps {
                echo "This is stage 3"
            }
        }
        stage("Stage 4") {
            steps {
                echo "This is stage 4"
            }
        }        
    }
}

