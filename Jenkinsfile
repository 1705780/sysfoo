pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compiling sysfoo app..'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'running unit tests here....'
        sh 'mvn clean test'
      }
    }

    stage('packag') {
      steps {
        echo 'package the artifact...'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}