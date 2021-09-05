pipeline {
  agent any
  tools {
        maven 'maven_381'
  }
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/chyuan530/devops-proj3.git', branch: 'main', credentialsId: ''])
      }
    }
    stage('Compile') {
      steps{
        withMaven {
          sh 'mvn clean compile'
        }
      }
    }
    stage('Test') {
      steps{
        withMaven {
          sh 'mvn test'
        }
      }
    }
    stage('Deploy') {
      steps{
        withMaven {
          sh 'mvn package'
        }
      }
    }
  }
  post {
      always {
          junit 'target/surefire-reports/*.xml'
      }
  }
}
