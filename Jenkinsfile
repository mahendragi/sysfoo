pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        docker {
          image 'maven:3.9.6-eclipse-temurin-17'
        }

      }
      steps {
        echo 'Compiling Maven application...'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      agent {
        docker {
          image 'maven:3.9.6-eclipse-temurin-17'
        }

      }
      steps {
        echo 'Running Maven tests...'
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      agent {
        docker {
          image 'maven:3.9.6-eclipse-temurin-17'
        }

      }
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