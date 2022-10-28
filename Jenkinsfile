pipeline {
  agent any
  environment {
    MYSQL_DB_CONNECTION_STRING = "jdbc:mysql://192.168.1.3:3306/my_app"
  }
  stages {
    stage('Update Database') {
      steps {
        step([$class: 'UpdateBuilder', installationName: 'liquibase3.8.9', username: 'mehroz', password: 'lahore', url: "${MYSQL_DB_CONNECTION_STRING}", changeLogFile: "my_app-wrapper.xml"])
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}
