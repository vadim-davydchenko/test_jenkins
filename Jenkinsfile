pipeline {
    agent any
    stages {
        stage('Run only if tag exist') {
            when {
                expression {
                    def tag = sh(script: 'git tag --points-at HEAD', returnStdout: true).trim()
                    return tag != ''
                }
            }
            steps {
                catchError {
                  script {
                        def tag = sh(
                            script: 'git tag --points-at HEAD',
                            returnStdout: true
                        ).trim()

                        echo "TAG_NAME is ${tag}"
                  }
                }
            }
        }
        stage('Run for tests') {
            when {
                expression {
                    def tag = sh(script: 'git tag --points-at HEAD', returnStdout: true).trim()
                    return tag == ''
                }
            }
            steps {
                echo "branch is " + env.GIT_BRANCH

            }
        }
    }
}

// pipeline {
//   agent any
//   stages {
//     stage('Deploy') {
//       when { buildingTag() }
//       steps {
//         sh "echo Deploying tag ${env.TAG_NAME} to production"
//       }
//     }
//   }
// }
