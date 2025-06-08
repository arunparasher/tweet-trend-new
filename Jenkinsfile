pipeline {
    agent {
        node {
            label 'maven-slave'
        }
    }
    stages {
        stage('git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/arunparasher/tweet-trend-new.git'
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