pipeline {
    agent any

    stages {
        stage('Checkout') {
           steps{
               checkout scm
           }
        }
        stage('Build') {
            steps {
                 dir('267142-java-first-ci-jo') {
                 bat 'mvn -B clean install'
                 }
            }
            
        }
        stage('Test') {
           steps {
                 dir('267142-java-first-ci-jo') {
                 bat 'mvn -B test'
                 }
        }
        stage('Publish Test Results') {
           steps {
               junit '267142-java-first-ci-jo/target/surefire-reports/*.xml'
           }
        }
    }
}
