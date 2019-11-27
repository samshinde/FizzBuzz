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
                sh 'mvn sonar:sonar -Dsonar.projectKey=pet-store -Dsonar.host.url=https://sonarcloud.io -Dsonar.organization=amol-example -Dsonar.login=684fc165294d8982b9a4837e9c2d24ef00b41e88'
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
          jacoco()
        }
    }
}
