pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "m399"
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'echo MAVEN version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/ramadevops2025/jenkins-hello-world.git'
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            steps {
               sh 'mvn test'
            }
        } 
    }
}
