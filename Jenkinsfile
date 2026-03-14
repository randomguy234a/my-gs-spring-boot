pipeline {
    agent any
    tools {
        maven 'M3'
    }
    stages {
        stage('Build Fat JAR') {
            steps {
                // 'bat' is the Windows version of 'sh'
                bat 'mvnw.cmd clean package -DskipTests'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
