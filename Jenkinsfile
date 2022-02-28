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

   
    

  }
}
