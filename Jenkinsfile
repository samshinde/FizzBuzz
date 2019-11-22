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
            agent {
                docker { 
                    image 'maven:3-alpine' 
                }
            }
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
            jacoco()
        }
    }
}
