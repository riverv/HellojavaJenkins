#!groovy
pipeline{
  agent any
  stages{
    stage('parallel'){
      failFast true
      parallel{
          stage('Java'){
            /*agent{
              dockerfile{
                filename 'Dockerfile.forjava' 
                dir 'docker-file'
              }
            }*/
            //if master branch then java compile
            when{branch 'master'}
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
          stage('test branch'){
            //if  est branch then java compile
            when{branch 'test'}
            steps{
              sh 'echo "into testbranch!"'
            }
          }
      }
    }
  }
  post{
    success{
      echo 'success!'
    }
    failure{
      echo 'failure..'
    }
  }
}
