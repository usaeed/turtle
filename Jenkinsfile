pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Display Build'
          }
        }
        stage('Build 2') {
          steps {
            echo 'Building 2'
          }
        }
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying ....'
          }
        }
        stage('Deploy2') {
          steps {
            echo 'Deploying .....'
          }
        }
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Testing ....'
          }
        }
        stage('Test2') {
          steps {
            echo 'Testing ....'
          }
        }
      }
    }
    stage('Calender') {
      steps {
        sh 'sh \'#!/usr/bin/sh -xe\\n env\''
      }
    }
    stage('QA') {
      steps {
        build(job: 'SampleBuildJob', quietPeriod: 3, wait: true)
      }
    }
    stage('Finished') {
      steps {
        sh 'echo "Hello world"'
      }
    }
  }
}