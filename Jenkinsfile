pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh '''./jenkins/build.sh
echo "I am a ${BUZZ_NAME}"'''
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