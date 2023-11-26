pipeline {   
    agent any
    tools {
        maven 'maven-3.9'
    }
    
    stages {
        stage("build jar") {
            steps {
                script{
                    echo "building the application...."
                    sh 'mvn package'

                }
            }
        }
        stage("build image") {
            steps {
                script{
                    echo 'building docker image....'
                    withcredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]){
                        sh 'docker build -t nnubiaawah1003/demo-app:jma-2.0 .'
                        sh 'echo $PASS | docker login -u $USER --password-stdin'
                        sh 'docker push nnubiaawah1003/demo-app:jma-2.0'

                    }
                }
                
            }
        }

        stage("deploy") {
            steps {
                script{
                    echo 'deploying the jma....'

                }  
            }
        }           
    }
} 
