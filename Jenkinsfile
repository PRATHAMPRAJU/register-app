pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'jdk17'
        maven 'maven3'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'git-cred', url: 'git@github.com:PRATHAMPRAJU/register-app.git'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

       }

       stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }      
   }
}
