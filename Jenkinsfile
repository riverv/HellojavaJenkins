#!groovy
pipeline{
  agent any
  stages{
    stage('parallel'){
      failFast true
      parallel{
          stage('Java'){
            steps{
              sh 'javac HelloWorld.java'
              sh 'echo java said:'
              sh 'java HelloWorld'
            }
          }
          stage('C'){
            steps{
              sh 'gcc -o LintTest LintTest.c'
              sh 'echo c said:'
            }
          }
          stage('C execute'){
            steps{
              sh './LintTest'
            }
          }
      }
    }
  }
}
