pipeline {
  agent any
  stages {
    stage('pull') {
      steps {
        git 'https://github.com/spring-projects/spring-petclinic.git'
      }
    }

    stage('Compile') {
      steps {
        build 'Petclinic'
      }
    }

    stage('SonarQube') {
      steps {
        waitForQualityGate true
      }
    }

    stage('deploy') {
      steps {
        archiveArtifacts 'jars'
      }
    }

  }
}