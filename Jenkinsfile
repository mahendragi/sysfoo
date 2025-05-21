pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Compiling Maven application...'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        echo 'Running Maven tests...'
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        echo 'Packaging Maven application...'
        sh 'mvn package -DskipTests'
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven 'Maven 3.9.6'
  }
}