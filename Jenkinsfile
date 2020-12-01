pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh './jenkins/build.sh'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      environment {
        BUZZ_NAME = 'Worker Bee'
      }
      steps {
        sh './jenkins/test-all.sh'
        junit '**/surefire-reports/**/*.xml'
      }
    }

  }
}