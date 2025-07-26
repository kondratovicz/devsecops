pipeline {
  agent any

  stages {
    stage('Build an Artifact') {
      steps {
        sh "mvn clean package -DskipTests=true"
        archive 'target/*.jar'
      }
    }
    stage('Test') {
      steps {
        sh "mvn test"
      }
      post { 
         always { 
           junit 'target/surefire-reports/*.xml'
           jacoco execPattern: 'target/jacoco.exec'
    }
  }
}}}
