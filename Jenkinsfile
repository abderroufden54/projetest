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
      stage('build image'){
      steps{
        script{
          sh 'npm install'
          withCredentials([usernamePassword(credentialsId:'firstimagedocker',passwordVariable:"pass",usernameVariable:"user")])
          {
            sh 'docker build -t firstimagedocker:2 .'
            sh 'docker login -u $user -p $pass'
            sh 'docker tag firstimagedocker:2 firstimagedocker:2'
            sh 'docker push abderraoufjs/firstimagedocker'
          }
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
