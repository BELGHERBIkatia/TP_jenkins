pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'gradle build'
        archiveArtifacts 'build/libs/*.jar'
      }
    }

    stage('test') {
      steps {
        bat 'gradle test'
      }
    }

    stage('documentation') {
      steps {
        bat 'gradle javadoc'
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
