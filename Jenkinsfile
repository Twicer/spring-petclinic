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
      }
    }

    stage('ARTIFACT') {
      steps {
        archiveArtifacts(artifacts: 'spring-petclinic-2.4.2.jar', onlyIfSuccessful: true)
      }
    }

    stage('DEPLOY') {
      steps {
        sh '''java -jar ./target/spring-petclinic-2.4.2.jar
 --server.port=8080'''
      }
    }

  }
}