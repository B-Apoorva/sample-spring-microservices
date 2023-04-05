pipeline{
agent any
stages{
  stage ("Git Checkout"){
    step{
    git credentialsId: 'c3c1a832-7172-4a60-b6a0-cbce7500901a', url: 'https://github.com/B-Apoorva/sample-spring-microservices.git'
    }
  }
  stage("Build"){
    step{
    sh 'mvn validate'
    }
    step{
     sh 'mvn clean compile'
    }
    step{
    sh 'mvn test'
    }
    step{
    sh 'mvn clean package'
    }
    step{
    sh 'mvn verify'
    }
  }
  stage("Deploy"){
    step{
    sh 'mvn deploy'
    }
  }
  }
}
