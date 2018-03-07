pipeline {
  agent {
    node {
      label 'docker-64'
    }
    
  }

  stages {
    stage('cargo build') {
      steps {
        sh '$HOME/.cargo/bin/cargo update && $HOME/.cargo/bin/cargo build'
      }
    }
    stage('client build') {
      parallel {
        stage('client build') {
          steps {
            sh 'cd src/bin && $HOME/.cargo/bin/cargo build --bin client --release'
          }
        }
        stage('server build') {
          steps {
            sh 'cd src/bin && $HOME/.cargo/bin/cargo build --bin server --release'
          }
        }
      }
    }
    stage('docker build') {
      steps {
        sh 'docker-compose build '
      }
    }
  }
}