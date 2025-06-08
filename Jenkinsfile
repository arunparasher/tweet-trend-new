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
        stage('Hello2') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hello3') {
            steps {
                echo 'Hello World'
            }
        }
    }
}