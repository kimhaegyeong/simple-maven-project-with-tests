node ('master') {
  checkout scm
  stage ('Build') {
    withMaven(maven: 'M3") {
      
      if (isUnix()) {
        sh 'mvn -Dmaven.text.failure.ignore clean package'
      }
      else {
        bat 'mvn -Dmaven.test.Failure.ignore clean package'
      }
    }
  }
  stage('Results') {
    jUnit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'
  }
}
