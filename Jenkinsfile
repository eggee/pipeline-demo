pipeline {
  agent any
  stages {
    stage('buzz build') {
      steps {
        sh '''echo "I am a ${BUZZ_NAME}"








./jenkins/build.sh'''
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }
    stage('Buzz test') {
      steps {
        sh './jenkins/test-all.sh'
        junit '**/surefire-reports/**/*.xml'
      }
    }
  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}