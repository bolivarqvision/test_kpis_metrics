pipeline {
  agent any
  stages {
    stage('Setup') {
      steps {
        script {
          echo "branch: ${env.GIT_BRANCH}"
        }
      }
    }

    stage('APP Build') {
      steps {
        sleep 300 
        echo "APP Build"
      }
    }

    stage('APP Quality'){
      steps {
        echo "APP Quality"
      }
    }

    stage('APP Unit Test') {
      steps {
        echo 'APP Unit Test'
      }
    } 
  }

  post {
    success {
      script {
        currentBuild.result = "SUCCESS"
        echo "postevent SUCCESS"
      }
    }

    failure {
      script {
        currentBuild.result = "FAILURE"
        echo "postevent FAILURE"
      }
    }

    unstable {
      script {
        currentBuild.result = "FAILURE"
        echo "postevent FAILURE"
      }
    }

    aborted {
      script {
        currentBuild.result = "FAILURE"
        echo "postevent FAILURE"
      }
    }
  }
}