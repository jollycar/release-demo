pipeline {
    agent any
    tools {
        maven 'Maven 3.6.0'
        jdk 'JDK8'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
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
