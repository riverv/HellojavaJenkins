#!groovy
pipeline{
  agent any 
  stages{
    stage('Build'){
      steps{
        sh 'echo "let s build"'
        sh 'javac HelloWorld.java'
      }
    }
    stage('Execute'){
      steps{
        sh 'java Hello'
      }
    }
  }
} 
