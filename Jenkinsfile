pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/bin/java' 
    }    
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
                    echo $JAVA_HOME
                '''
                
            }
        }
        stage("Stage 2") {
            steps {
                echo "This is stage 2"
                withGroovy(tool:'3.0.8') {
                    sh 'groovy --version'                    
                }
                withGroovy {
                    script{
                        for (int i = 1; i <= 10; i++) {
                            println(i)
                        }                
                    }
                }
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

