node {
  stage("Checkout") {
    git url: "https://github.com/minjung00z/jenkins1.git",branch:'main',credentialId:"github-checkout-token"
  }

  stage("Build") {
      try {
          bat 'npm install'
          bat 'npm run build'
      } catch (e) {
          error '빌드 실패: $(e)'
      }
  }

  stage('Test') {
      def testsPassed = bat(script: 'set CI=true && npm test -- --passWithNoTests',returnStatus: true)
      if (testsPassed != 0) {
          error '테스트 실패!'
      }
  }

  stage('Deploy') {
      if (env.BRANCH_NAME == 'main') {
          bat 'npm start'
      } else {
          echo 'Main 브랜치가 아니어서 실행 생략'
      }
    }
  }
      
