pipeline {
  agent any
  tools {
      gradle "gradle-8.14.1"
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
        echo 'executing gradle...'
        withGradle() {
          echo 'check gradle version...'
          sh 'gradle -v'  // --type basic
          sh 'pwd'
          sh 'ls -la'
        //   echo 'init Gradle...'
        //   sh 'gradle init'  // --type basic
          // sh 'ls ./gradlew'
          // sh './gradlew -v'
        }
      }
    }
  }
}
