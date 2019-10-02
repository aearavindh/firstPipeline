pipeline{
   agent any
      stages{
         stage('One'){
            steps{
               echo 'Hi, This is Aravindh A E'
            }
         }
         stage('Two'){
            steps{
               input('Do you want to proceed?')
            }
         }
         stage('Three'){
            steps{
               when{
                   not{
                      branch "master"
                   }
               }
               steps{
                  echo "Hello"
               }
            }
         }
         stage('Four'){
            parallel{
               stage('Unit Testing'){
                  steps{
                     echo 'Running the unit tests...'
                  }
               }
               stage('Integration Testing'){
                  agent{
                     docker{
                        reuseNode false
                        image 'ubuntu
                     }
                  }
                  steps{
                     echo 'Running the integration test...'
                  }
                  
               }
            }
         }
      }
}
