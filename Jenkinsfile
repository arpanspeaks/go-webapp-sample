pipeline {
  agent any
  tools {
    go 'go-1.17'
  }
  environment {
    GO111MODULE='on'
  }
  stages {
    stage('dev') {
      steps {
        sh 'go test ./...'
      }
    }
    stage('build') {
      steps {
        git 'https://github.com/arpanspeaks/go-webapp-sample.git'
        sh 'go build .'
        sh './go-webapp-sample'
      }
    }
    stage('run') {
      steps {
        git 'https://github.com/arpanspeaks/go-webapp-sample.git'
        sh 'go build .'
        sh 'cd /var/lib/jenkins/workspace/sample-go-pipeline && sample-go-pipeline &'
      }
    }

  }
}
