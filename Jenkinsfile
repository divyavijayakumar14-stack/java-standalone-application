pipeline {
    agent any

  
    stages {
        stage('Checkout') {
            steps{
                checkout scm
            }
        }
        stage('Build') {
            steps{
                dir('267142-java-first-ci-job'){
                    bat 'mvn -B clean install'
                }
            }
        }
        stage('Test') {
           steps{
                dir('267142-java-first-ci-job'){
                    bat 'mvn -B test'
                }
         }
        }
        stage('Publish Test Results') {
            // write your logic here
           steps{
               junit '267142-java-first-ci-job/target/surefire-reports/*.xml'
           }
        }
    }
}
