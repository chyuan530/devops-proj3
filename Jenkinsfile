pipeline {
  environment {
    mvn = '/home/chyuan/maven/apache-maven-3.8.1/bin//mvn:'
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/chyuan530/devops-proj3.git', branch: 'main', credentialsId: ''])
      }
    }
    stage('Compile') {
      steps{
        sh '$mvn clean compile'
      }
    }
    stage('Test') {
      steps{
        sh '$mvn test'
      }
    }
    stage('Deploy') {
      steps{
        sh '$mvn package'
      }
    }
  }
}
