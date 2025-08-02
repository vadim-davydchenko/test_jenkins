pipeline {
  agent any
  stages {
    stage('Deploy') {
      when { buildingTag() }
      steps {
        sh "echo Deploying tag ${env.TAG_NAME} to production"
      }
    }
  }
}
