pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'gradle build'
          bat 'gradle javadoc'
         bat 'gradle test'
        archiveArtifacts 'build/libs/*.jar'
      }
    }

   

  


    stage('deploy') {
      steps {
        bat 'gradle jar'
        bat 'gradle publish'
      }
    }

    stage('Slack') {
      steps {
        slackSend(baseUrl: 'https://hooks.slack.com/services/', token: 'T02RPFZGBHP/B02SUM6RKCK/A00xKjCwfofPcyQAZ0i5dP5F', message: 'slack notification')
      }
    }

  }
}
