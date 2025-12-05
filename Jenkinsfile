pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build') {
      steps {
        echo "Building..."
        sh 'mkdir -p target'
        sh 'echo "artifact created" > target/output.txt'
      }
    }

    stage('Test') {
      steps {
        echo "Running tests..."
        sh 'echo "1 test passed"'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'target/**', fingerprint: true
      }
    }

    stage('Deploy') {
      steps {
        echo "Deploying to staging..."
      }
    }
  }
}
