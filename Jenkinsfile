pipeline {
  agent any
  stages {
    stage('get code') {
      steps {
        git(url: 'https://github.com/SMS2425/spring3-mvc-maven-xml-hello-world.git', branch: 'master', changelog: true, poll: true)
      }
    }

    stage('maven') {
      steps {
        sh 'mvn package'
      }
    }

  }
}