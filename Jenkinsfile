pipeline {
    agent any  
    
    tools {
        maven 'sonarmaven'
        jdk 'JAVA_HOME'
    }

    environment {
        JAVA_HOME = "C:\\Program Files\\Java\\jdk-17"
        MAVEN_PATH = "C:\\Users\\prabh\\Downloads\\apache-maven-3.9.9\\bin"
        PATH = "${JAVA_HOME}\\bin;${MAVEN_PATH};C:\\Windows\\System32;C:\\Windows"  
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kavya013/kavya_jenkins_task6_method2and3' 
            }
        }

        stage('Verify Tools') {
            steps {
                script {
                    bat 'java -version'
                    bat 'mvn -version'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    bat 'mvn clean compile'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    bat 'mvn test'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and tests passed successfully!'
        }
        failure {
            echo 'Build or tests failed. Check the logs!'
        }
    }
}
