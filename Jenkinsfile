pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/Myya33/flask.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t myya33/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u myya33 -p dckr_pat_3IsZ-C6m-WedZX3TTXKMjp1bydY'
      }
    }

    stage('Docker Psuh') {
      steps {
        sh 'docker push myya33/flask_app'
      }
    }

  }
}