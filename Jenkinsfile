pipeline {

    agent any

    tools {
        maven'Maven'
    }

    stages {

        stage('build') {
            steps {
                sh 'mvn --version'
                echo 'Maven version success'
            }
        }

        stage('test') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('deploy') {
            steps {
                sh 'mvn test'
            }
        }

        stage('run') {
            steps {
                sh 'mvn package'
            }
        }

        stage('new') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }

    post {

        success {
            echo 'Java successfully run'
        }

        failure {
            echo 'Java failure'
        }
    }
}
