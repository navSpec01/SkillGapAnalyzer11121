pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the SkillGap Analyzer source code.'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn clean compile'
                    } else {
                        bat 'mvn clean compile'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn test'
                    } else {
                        bat 'mvn test'
                    }
                }
            }
        }

        stage('Package') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn package'
                    } else {
                        bat 'mvn package'
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: SkillGap Analyzer built, tested and packaged.'
        }
        failure {
            echo 'FAILURE: Check the stage logs and fix the error.'
        }
    }
}
