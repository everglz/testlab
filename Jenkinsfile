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
        emailext(subject: 'Compilaci�n', attachLog: true, body: 'Se requiere la Aprobaci�n', to: 'everglz')
      }
    }
  }
  triggers {
    cron('H 3 * * *')
  }
}