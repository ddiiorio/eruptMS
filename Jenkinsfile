pipeline {
  agent any
  stages {
    environment { 
        containerName= sh (returnStdout: true, script: 'echo erupt$GIT_BRANCH').trim()
    }
    stage('build container') {
      steps {
        sh 'sudo docker stop eruptTEST'
        sh 'sudo docker rm eruptTEST'
        sh 'sudo docker-compose -f build.yml up --build -d'
      }
    }
    stage('build containername') {
      steps {
        sh 'echo Container name is $containerName'
        sh 'echo branch name is ${GIT_BRANCH}'
        sh 'echo erupt$GIT_BRANCH'
        sh 'echo $containerName'
      }
    }
  }
}
