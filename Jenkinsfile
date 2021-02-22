pipeline {
  agent any
  stages {
    stage('Build-Image') {
      steps {
        sh 'docker build -t srirammk18/jenkins-docker":$BUILD_NUMBER" .'
      }
    }
      stage ('Push-Image') {
        steps {
        withDockerRegistry([ credentialsId: "dockerhub_id", url: "" ]) {
          sh 'docker push srirammk18/jenkins-docker":$BUILD_NUMBER"'
        }
      }
    }
  }
}
