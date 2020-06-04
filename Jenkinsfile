pipeline {
  agent {
    docker {
      image 'golang'
    }
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
