pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/prxj10/maven-to-gradle.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar build/libs/maven-to-gradle-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo 'Gradle build successful!'
        }
        failure {
            echo 'Gradle build failed!'
        }
    }
}
