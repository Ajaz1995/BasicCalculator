pipeline {
    agent { label 'agent1'}
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac BasicCalculator.java'
                sh 'jar cf BasicCalculator.jar BasicCalculator.class'
                sh 'pwd'
            }
        }
      
        stage('Execute Calculator') {
            steps {
                sh 'java -jar BasicCalculator.jar'
            }
         }
     }
        post {
        success {
            archiveArtifacts artifacts: 'BasicCalculator.jar'
            
            }
        }
    }
