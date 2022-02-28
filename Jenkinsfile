pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat(script: 'lancement de build Gradle', returnStatus: true)
      }
    }
stage('Generate HTML report') {
        cucumber buildStatus: 'UNSTABLE',
                reportTitle: 'My report',
                fileIncludePattern: '**/*.json',
                trendsLimit: 10,
                classifications: [
                    [
                        'key': 'Browser',
                        'value': 'Firefox'
                    ]
                ]
    }
  }
}
