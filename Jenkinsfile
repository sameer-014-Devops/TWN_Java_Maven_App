def gv

pipeline {   
    agent any
    tools {
        'maven-3.9'
    }
    stages {
        stage("init") {
            steps {
                script{
                    gv = load "script.groovy"

                }
            }
        }
        stage("build jar") {
            steps {
                script{
                    gv.buildJar()

                }
            }
        }
    
        stage("build image") {
            steps {
                script{
                    gv.buildImage()

                }
                
            }
        }

        stage("deploy") {
            steps {
                script{
                    gv.deployApp()

                }  
            }
        }           
    }
} 
