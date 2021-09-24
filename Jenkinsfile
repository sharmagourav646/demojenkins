pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh 'echo "this is a test step"'
        sh 'echo "this is test step 2"'
      }
    }

    stage('build') {
      steps {
        sh 'echo "this is build step"'
      }
    }

    stage('deploy on test') {
      steps {
        echo 'depploy on test called'
      }
    }

    stage('confirmation') {
      steps {
        input(message: 'do you want it on production ?', id: 'confirm', ok: 'ok')
      }
    }

    stage('prod') {
      steps {
        echo 'deploy on prod called'
      }
    }

  }
}