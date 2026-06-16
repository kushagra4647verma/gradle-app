pipeline {
    agent any

    tools {
        gradle 'Gradle'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'gradle clean build'
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
            }
        }

        stage('Output') {
            steps {
                sh 'gradle run'
            }
        }
    }

    post {

        success {
            echo 'Gradle Build Successful'
        }

        failure {
            echo 'Gradle Build Failed'
        }
    }
}
