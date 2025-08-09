pipeline{
    agent {label 'jenkins-agent'}
    tools{
      jdk 'JAVA21'
      maven 'Maven3'
    }
    stages{
      stage("clean Workspace"){
        steps{
          cleanWs()
        }
      }
      stage("checkout From SCM"){
        steps{
          git branch: 'main' , credentialsId: 'github', url: 'https://github.com/DishantThakur21/devops-project'
        }
      }
      stage("Build application"){
        steps{
          sh "mvn clean package"
        }
      }
      stage("test application"){
        steps{
          sh "mvn test"
        }
      }
    }
}
