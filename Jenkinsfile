pipeline {
  agent any

  environment {
    FIREBASE_TOKEN = '1//06PkT8YS7y_zECgYIARAAGAYSNwF-L9IrEh4mLmGgepA3zJgug9LfmpGeImQSiScj9ZVqtxsUdnj7plxk7P2PbVn2c9fS_01qOjE'
  }

  stages {
    stage('Install Firebase Tools') {
      steps {
        sh 'npm install -g firebase-tools'
      }
    }

    stage('Deploy to Testing') {
      steps {
        sh 'firebase use testing --token "$FIREBASE_TOKEN"'
        sh 'firebase deploy --only hosting --token "$FIREBASE_TOKEN"'
      }
    }

    stage('Deploy to Staging') {
      steps {
        sh 'firebase use staging --token "$FIREBASE_TOKEN"'
        sh 'firebase deploy --only hosting --token "$FIREBASE_TOKEN"'
      }
    }

    stage('Deploy to Production') {
      steps {
        sh 'firebase use production --token "$FIREBASE_TOKEN"'
        sh 'firebase deploy --only hosting --token "$FIREBASE_TOKEN"'
      }
    }
  }
}
