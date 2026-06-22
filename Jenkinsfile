pipline {
  agent any
    stages {
      stage("Checkout") {
        steps {
          checkout scm
        }
      }
      stage("Install") {
        steps {
          bat 'npm install'
        }
      }
      stage("Test") {
        steps {
          //bat 'npm test'
          bat 'set CI=true && npm test'
        }
      }
      stage("Start") {
        when {
          branch 'main'
        }
        steps {
          bat 'npm start'
        }
      }
    }
    post {
      success {
        echo 'Pipline 성공적으로 완료!'
      }
      failure {
        echo 'Pipline 실패!!'
      }
    }
  }
