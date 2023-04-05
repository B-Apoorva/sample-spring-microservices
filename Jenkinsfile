pipeline{
agent any
stages{
  stage ("Git Checkout"){
    steps{
    git credentialsId: 'c3c1a832-7172-4a60-b6a0-cbce7500901a', url: 'https://github.com/B-Apoorva/sample-spring-microservices.git'
    }
  }
  stage("Build"){
    steps{
    sh 'mvn validate'
    }
    steps{
     sh 'mvn clean compile'
    }
    steps{
    sh 'mvn test'
    }
    steps{
    sh 'mvn clean package'
    }
    step{
    sh 'mvn verify'
    }
  }
  stage("Deploy"){
    steps{
    sh 'mvn deploy'
    }
  }
  }
}
