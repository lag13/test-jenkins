pipeline {
  parameters {
    // string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
    choice(description: 'Deployment Environment', choices: ['dev', 'prod', 'test-label'], name: 'DEPLOY_ENV')
  }
  environment {
    HEY_THERE = 'buddy'
  }
  agent {
    docker {
      image 'golang'
      label "${params.DEPLOY_ENV}"
    }
  }
  stages {
    stage('build') {
      steps {
        sh 'go version'
      }
    }
    // stage('Sanity check') {
    //   steps {
    //     // the build will pause here and wait for you to click proceed
        
    //     // input "the build is paused now, do you want to keep going?"
    //   }
    // }
    stage('sh commands') {
      steps {
        sh 'echo hey'
        sh 'echo there'
        sh 'echo this prints the env variable $HEY_THERE'
        sh "echo and so does this $HEY_THERE"
        sh 'printenv'
      }
    }
    stage('create file') {
      steps {
        sh 'echo hey > asdf'
      }
    }
    stage('look at the param') {
      steps {
        // seems that double quotes are needed to get a parameter
        echo "Hello ${params.DEPLOY_ENV}"
        echo 'Hello ${params.DEPLOY_ENV}'
        echo "Hello ${params.PERSON}"
      }
    }
  }
  post {
    always {
      echo 'this always runs'
      sh 'echo another step'
    }
  }
}
