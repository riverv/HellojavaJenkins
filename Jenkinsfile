#!groovy
pipeline{
  agent any
  stages{
    stage('parallel'){
      failFast true
      parallel{
          stage('Java'){
            agent{
              dockerfile{
                filename 'Dockerfile'
                dir 'java-docker'
                label 'javadocker'
              }
            }
            steps{
              sh 'javac HelloWorld.java'
              sh 'echo java said:'
              sh 'java HelloWorld'
            }
          }
          stage('C'){
            steps{
              sh 'gcc -o LintTest LintTest.c'
              sh './LintTest'
           }
          }
      }
    }
  }
}
