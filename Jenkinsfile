pipeline {
  agent any

  stages {
    stage('build') {
      steps {
        script {
          sh 'npm install'
          echo "built"
        }
      }
    }

    stage('build image') {
      steps {
        script {
          sh 'npm install'
          withCredentials([usernamePassword(credentialsId: 'firstimagedocker', passwordVariable: "pass", usernameVariable: "user")]) {
            sh 'docker build -t firstimagedocker:2 .'
            sh "echo \$pass | docker login -u \$user --password-stdin"
            sh 'docker tag firstimagedocker:2 abderraoufjs/firstimagedocker:2'
            sh 'docker push abderraoufjs/firstimagedocker'
          }
        }
      }
    }

    stage('deploy') {
      steps {
        script {
          echo "deployed"
        }
      }
    }
  }
}
