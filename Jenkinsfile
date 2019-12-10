pipeline {
    agent any
    tools {
        maven 'Maven 3.6.0'
        jdk 'java-11-openjdk'
    }
    stages {
        stage('Build dev branch') {
            when {
                allOf {
                    not {
                        buildingTag()
                    }
                    not {
                        branch 'master'
                    }
                }
            }
            steps {
                echo 'Building dev branch'
            }
        }
        stage('Build prod branch') {
            when {
                buildingTag()
            }
            steps {
                echo 'Building prod branch'
            }
        }
        stage('Publish dev') {
            when {
                branch 'dev'
            }
            steps {
                echo 'Publish dev'
            }
        }
        stage('Publish prod') {
            when {
                buildingTag()
            }
            steps {
                echo 'Publish prod'
            }
        }
        stage('Skip Publish') {
            when {
                allOf {
                    not {
                        buildingTag()
                    }
                    not {
                        branch 'master'
                    }
                }
            }
            steps {
                echo 'Skip publish'
            }
        }
    }
}
