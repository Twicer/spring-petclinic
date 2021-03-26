pipeline {
  agent {
    node {
      label 'instance1'
    }

  }
  stages {
    stage('CHECKOUT') {
      parallel {
        stage('CHECKOUT') {
          steps {
            echo '1'
          }
        }

        stage('Environment') {
          steps {
            sh '''sudo apt update
sudo apt -y install maven'''
          }
        }

      }
    }

    stage('BUILD') {
      steps {
        sh 'mvn package'
        sh 'ls -la'
      }
    }

    stage('CREATE ') {
      steps {
        echo '1'
        sh '''cd mvnw
mvn package
'''
        sh 'java -jar target/*.jar'
        sh 'mvn tomcat7:run'
      }
    }

    stage('ARTIFACT') {
      steps {
        echo 'error'
      }
    }

    stage('DEPLOY') {
      steps {
        sh 'java -jar ./spring-petclinic1.jar --server.port=8080'
      }
    }

  }
}