pipeline {
    agent any

    tools {
        gradle 'gradle'   // use Jenkins-installed Gradle
        jdk 'JDK'         // use Jenkins JDK
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/prxj10/maven-to-gradle.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
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
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
