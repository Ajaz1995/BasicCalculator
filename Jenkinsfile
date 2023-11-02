pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cfm BasicCalculator.jar Manifest.txt BasicCalculator.class'
                sh 'mv BasicCalculator.jar /var/jenkins_home/BasicCalculator.jar'
            }
        }
      
        stage('Execute HelloWorld') {
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
