pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh './jenkins/build.sh'
      }
    }

    stage('Buzz Test') {
      steps {
        sh './jenkins/test-all.sh'
      }
    }

    stage('Archive Artefacts ') {
      steps {
        archiveArtifacts(artifacts: 'my-app.zip', caseSensitive: true)
      }
    }

  }
}