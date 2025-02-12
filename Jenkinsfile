pipeline {
    agent any  
    
    tools {
        maven 'sonarmaven'
        jdk 'JAVA_HOME'
    }

    environment {
        MAVEN_PATH = 'C:\\Users\\prabh\\Downloads\\apache-maven-3.9.9\\bin'
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'
        PATH = "${MAVEN_PATH};${JAVA_HOME};${env.PATH}"  
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kavya013/kavya_jenkins_task6_method2and3' 
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
