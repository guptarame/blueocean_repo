pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'build pipeline 112'
      }
    }

    stage('test') {
      steps {
        echo 'test pipeline'
      }
    }

    stage('stage') {
      parallel {
        stage('stage1_parallel') {
          steps {
            echo 'stage pipeline 1 parallel'
          }
        }

        stage('stage2_pipeline') {
          steps {
            echo 'stage 2 pipeline parallel'
          }
        }

      }
    }

    stage('prod1') {
      parallel {
        stage('prod1') {
          steps {
            echo 'production1'
            input(message: 'is it ok to continue', id: 'ok', ok: 'ok', submitter: 'ramesh', submitterParameter: 'ramesh')
          }
        }

        stage('prod2') {
          steps {
            echo 'prod2'
          }
        }

      }
    }

    stage('prod') {
      steps {
        echo 'prod'
      }
    }

  }
  post {
    always {
      echo 'I will always say Hello again!'
    }

    success {
      echo 'I will success again!'
    }

    failure {
      echo 'thats fail'
    }

  }
}