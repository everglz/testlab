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
    stage('Aprove') {
      steps {
        input(message: 'Aprobar', submitter: 'everglz')
      }
    }
  }
  triggers {
    cron('H 15 * * *')
  }
}