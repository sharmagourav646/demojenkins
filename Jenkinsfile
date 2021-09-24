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
      parallel {
        stage('prod') {
          steps {
            echo 'deploy on prod called'
          }
        }

        stage('prod2') {
          steps {
            echo 'prod2 called'
          }
        }

        stage('prod3') {
          steps {
            echo 'prod3 called'
          }
        }

      }
    }

    stage('end') {
      steps {
        echo 'the end.'
      }
    }

  }
}