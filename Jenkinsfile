#!/usr/bin/env groovy

pipeline {

    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps{
                echo "Checkout Completed...."
            }
        }
        stage('Build') {
            steps{
                echo "Build Completed"
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy Completed"
            }
        }  
    }

    post {  
        always {
          junit "**/build/test-results/*.xml"
          step([
              $class           : 'JacocoPublisher',
              execPattern      : 'build/jacoco/jacoco.exec',
              classPattern     : 'build/classes/main',
              sourcePattern    : 'src/main/java',
              exclusionPattern : '**/*Test.class'
          ])
        }
    }
}
