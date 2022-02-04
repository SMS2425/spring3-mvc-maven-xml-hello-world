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
    stage('deploy'){
            steps{
                withCredentials([usernameColonPassword(credentialsId: 'tomcat_credentials', variable: 'tomcat_credentials')]) {   
            	sh "curl -v -u ${tomcat_credentials} -T /var/lib/jenkins/workspace/pipeline_project1/target/DemoMavenProject.war 'http://ec2-3-109-123-216.ap-south-1.compute.amazonaws.com:8081/manager/text/deploy?path=/pipeline1project&update=true'"
            }
        }

  }
}
