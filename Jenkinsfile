pipeline {
    agent any

    stages {
        stage('Test/Build Code') {
            agent {
                docker {
                    image 'eclipse-temurin:25'
                }
            }
            steps {
                sh './mvnw package -s jcenter-maven-settings.xml'
            }
        }

        stage('Build Image') {
            agent {
                node {
                    label 'built-in' 
                }
            }
            steps {
                sh '/usr/bin/docker build -t petclinicc:${BUILD_NUMBER} .'
            }
        }
    }
}