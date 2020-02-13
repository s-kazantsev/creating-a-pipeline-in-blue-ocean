pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
        input(message: 'Finished using the web site?', id: '777', ok: 'ok_param', submitter: 'sub_param', submitterParameter: 'SubParam_param')
      }
    }

  }
}