pipeline {
    agent any
    tools {
        maven 'Maven 3.6.0'
        jdk 'java-11-openjdk'
    }
    stages {
        stage('Build branch') {
            steps {
                echo 'Building a branch'
                sh 'mvn clean package'
            }
        }
        stage('Build tag') {
            when {
                buildingTag()
            }
            steps {
                echo 'Building a tag'
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying build ${env.BUILD_ID}..."
            }
        }
    }
}
