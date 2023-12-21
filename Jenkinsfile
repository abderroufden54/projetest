pipeline{
  agent any
  stages{
    stage('build'){
      steps{
        script{
          sh 'npm install'
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
