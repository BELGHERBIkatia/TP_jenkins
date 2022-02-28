pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat(script: 'lancement de build Gradle', returnStatus: true)
          archiveArtifacts 'build/libs/*.jar'
      }
    }
     stage('deploy') {
      steps {
        bat 'gradle jar'
      }
    }

    stage('Slack') {
      steps {
        slackSend(baseUrl: 'https://hooks.slack.com/services/', token: 'T02RPFZGBHP/B02SUM6RKCK/A00xKjCwfofPcyQAZ0i5dP5F', message: 'slack notification')
      }
    }

    

  }
}
