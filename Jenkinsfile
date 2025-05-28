pipeline {
  agent any
  tools {
      gradle 8.14.1
  }
  stages {
    stage("run frontend"){
      steps {
        echo 'executing yarn...'
        nodejs('NodeJS_10.17') {
          sh 'yarn install'
        }
      }
    }
    stage ("run backend") {
      steps  {
        echo 'init Gradle...'
        sh 'gradle init'  // --type basic
        echo 'executing gradle...'
        withGradle() {
          echo 'check gradle version...'
          sh './gradlew -v'
        }
      }
    }
  }
}
