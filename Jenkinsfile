pipeline {
    agent {
        node {
            label 'maven-slave'
        }
    }
    environment{
        PATH = "/opt/apache-maven-3.9.10/bin:$PATH"
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn clean install -DskipTests'
            }
        }
          stage('SonarQube analysis') {
                withSonarQubeEnv(credentialsId: 'sonar-token', installationName: 'sonar-server') { // You can override the credential to be used, If you have configured more than one global server connection, you can specify the corresponding SonarQube installation name configured in Jenkins
                sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.11.0.3922:sonar'
                }
            }
        stage('Hello3') {
            steps {
                echo 'Hello World'
            }
        }
    }
}