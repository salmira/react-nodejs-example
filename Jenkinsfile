pipeline {
  agent any
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
        echo 'executing gradle...'
        withGradle() {
          echo 'check gradle version...'
          sh './gradlew -v'
        }
      }
    }
  }
}
