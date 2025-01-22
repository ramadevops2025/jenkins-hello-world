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
                archiveArtifacts artifacts: 'target/hello-demo-*.jar'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
               // junit keepProperties: true, keepTestNames: true, stdioRetention: '', testResults: 'target/surefire-reports/TEST-*.xml'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        } 
    }
}
