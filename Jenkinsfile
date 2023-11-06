pipeline {
    agent { label 'agent1'}
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac BasicCalculator.java'
                sh 'jar cf BasicCalculator.jar BasicCalculator.class'
                sh 'mv BasicCalculator.jar /var/jenkins_home/BasicCalculator.jar'
            }
        }
      
        stage('Execute Calculator') {
            steps {
                sh 'cp /var/jenkins_home/BasicCalculator.jar .'
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
