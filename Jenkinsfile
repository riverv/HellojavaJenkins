#!groovy
pipeline{
  agent any
  stages{
    stage('parallel'){
      when{
        branch master
      }
      failFast true
      parallel{
          stage('Java'){
            /*agent{
              dockerfile{
                filename 'Dockerfile.forjava' 
                dir 'docker-file'
              }
            }*/
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
              sh 'splint LintTest.c'
           }
          }
      }
    }
    stage('test'){
      steps{
        echo 'this is test branch! so not build hahaha...'
      }
    }
  }
  post{
    success{
      echo 'success!'
    }
    failure{
      echo 'failure...'
    }
  }
}
