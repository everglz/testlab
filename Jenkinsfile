pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        bat 'C:\\Users\\Cleber\\Desktop\\Jenkins\\install.bat'
      }
    }
    stage('SendMail') {
      steps {
        emailext(subject: 'Compilación', attachLog: true, body: 'Se requiere la Aprobación', to: 'everglz')
      }
    }
  }
  triggers {
    cron('H 3 * * *')
  }
}