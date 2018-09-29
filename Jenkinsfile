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
    stage('Commit') {
      parallel {
        stage('Commit') {
          steps {
            bat 'C:\\Users\\Cleber\\Desktop\\Jenkins\\build.bar'
          }
        }
        stage('SendMail') {
          steps {
            emailext(subject: 'Aprobar Commit', to: 'laugza', body: 'Favor de Aprobar el Commit', attachLog: true)
          }
        }
      }
    }
  }
  triggers {
    cron('H 15 * * *')
  }
}