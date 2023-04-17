pipeline {
  environment{
    registry = 'myya33/flask_app'
    registryCredentials = 'docker'
    cluster_name = 'skillstorm'
  }
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/Myya33/flask2.git', branch: 'main')
      }
    }
  stage('Build Stage') {
      steps {
        script {
          dockerImage = docker.build(registry)
        }
      }
  }
  stage('Deploy Stage') {
      steps {
        script {
          docker.withRegistry('', registryCredentials) {
                dockerImage.push()
          }
        }
      }
    }
  }
}
