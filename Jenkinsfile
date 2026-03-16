pipeline {
    agent any

    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/pankajpendavale3/jenkins-ci-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }

    }
}
