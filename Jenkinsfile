#!groovy
pipeline{
  agent any 
  stages{
          stage('Java'){
            steps{
              sh 'javac HelloWorld.java'
              echo 'java said:'
              sh 'java HelloWorld'
            }          
          }
          stage('C'){
            steps{
              sh 'gcc -o LintTest LintTest.c'
              echo 'c said:'
              sh './LintTest'
            }
          }
  }
} 
