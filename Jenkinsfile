pipeline {
  agent any
  environment {
    MYSQL_DB_CONNECTION_STRING = "jdbc:mysql://localhost:3306/my_app"
  }
  stages {
    stage('Update Database') {
      steps {
        step([$class: 'UpdateBuilder', installationName: 'Liquibase', credentialsId: 'mysql_mehroz', url: "${MYSQL_DB_CONNECTION_STRING}", changeLogFile: "my_app-wrapper.xml"])
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}
