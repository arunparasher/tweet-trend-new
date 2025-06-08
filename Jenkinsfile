pipeline {
    agent {
        node {
            label 'maven-slave'
        }
    }
    environment {
        PATH = "/opt/apache-maven-3.9.10/bin:$PATH"
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('SonarQube analysis') {  // Correctly placed stage block
            steps {
                withSonarQubeEnv(credentialsId: 'sonar-token', installationName: 'sonar-server') {
                    sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.11.0.3922:sonar'
                }
            }
        }
        stage('Hello3') {
            steps {
                echo 'Hello World'
            }
        }
    }
}