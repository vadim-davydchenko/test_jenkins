pipeline {
  agent any
  stages {
    stage('Only on tag') {
      when { buildingTag() }
      steps { echo "Deploying tag ${env.TAG_NAME}" }
    }
  }
}
