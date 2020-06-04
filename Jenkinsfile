pipeline {
  agent {
    docker {
      image 'golang'
      label 'test-label'
    }
  }
  environment {
    HEY_THERE = 'buddy'
  }
  stages {
    stage('build') {
      steps {
        sh 'go version'
      }
    }
    stage('sh commands') {
      steps {
        sh 'echo hey'
        sh 'echo there'
        sh 'echo this prints the env variable $HEY_THERE'
        sh "echo and so does this $HEY_THERE"
        sh 'printenv'
      }
    }
  }
  post {
    always {
      echo 'this always runs'
      echo 'I guess stuff in the post section will just be plain sh stuff since I do not explicitly say "sh" on these steps'
    }
  }
}
