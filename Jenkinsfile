pipeline {
  agent any
  triggers {
    cron('H 3 * * *')
  }
  stages {
    stage('Install') {
      steps {
        bat 'C:\\Users\\Cleber\\Desktop\\Jenkins\\install.bat'
      }
    }
  }
}
