pipeline{
  agent any
  stages{
    stage('build'){
      steps{
        script{
          npm ci()
          echo "builded"
        }
      }
    }
     stage('deploy'){
       steps{
         script{
           echo "deployed"
         }
       }
    }
  }
}
