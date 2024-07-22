pipeline {
    agent { label : 'jenkins-agent'}
    tools {
        jdk 'java17'
        maven 'maven3'
    }
    stages {
        stage("Clean Workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Git Checkout") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/GURUGASTGAR/register-app.git'
            }
        }

        stage("build applicatoin") {
            steps {
                sh "mvn clean package"
            }
        }

        stage("test application") {
            steps{
                sh "mvn test"
            }
        }
        


    }
}