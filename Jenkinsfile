pipeline {
    agent any
    triggers {
        GenericTrigger(
            regexpFilterText: '$ref',
            regexpFilterExpression: '^refs/tags/.*$',
            causeString: 'Tag push: $ref'
        )
    }

    stages {
        stage('Deploy tag') {
            steps {
                sh 'echo Deploying ${ref} to production'
            }
        }
    }
}
