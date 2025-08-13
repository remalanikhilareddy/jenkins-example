pipeline{
  agent{ label 'Jenkins-agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage("Cleanup Workspace"){
      steps{
        cleasWs()
      }
    }
    stage("Checkout from SCM"){
      steps{
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/remalanikhilareddy/jenkins-example'
      }
    }
    stage("Build Application"){
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

    
