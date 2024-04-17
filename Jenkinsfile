pipeline {
  agent  {label 'jenkins-agent'}
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages { 
    stage("Cleanup Workspace"){
           steps {
           cleanWs()
           }
    }
    stage("Checkout from SCM"){
          steps{
            git branch: 'main', credentialsID: 'github', url: 'https://github.com/DSR5/register-app.git'
          }
    }
    stage("Bulid Application"){
          steps{
            sh "mvn clean package"
          }
    }
    stage("Test Application"){
          steps{
            sh "mvn test"
          }
    }

  }
} 
