pipeline {
    agent any

    tools {
        gradle 'Gradle'   // must match Jenkins config EXACTLY
        jdk 'jdk'         // change if your config name is different
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
                sh 'gradle run'
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
