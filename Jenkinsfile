#!/usr/bin/env groovy

pipeline {

  agent any

  options {
    timestamps()
  }

  stages {
    stage('Checkout') {
        echo "Checkout Completed...."
    }
    stage('Build') {
        echo "Build Completed"
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
        echo "Deploy Completed"
    }  
  }
}
