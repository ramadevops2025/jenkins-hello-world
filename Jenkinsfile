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
               sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            steps {
                script {
                for (int i = 0; i < 60; i++) {
                    echo "$(i+1)"
                    sleep 1
                }
               sh 'mvn test'
                }
            }
        } 
    }
}
