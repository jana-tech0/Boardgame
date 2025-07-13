pipeline {
    agent any

    tools {
        jdk 'jdk11'        // ✅ Must match the name in "Manage Jenkins > Global Tool Configuration"
        maven 'maven3'     // ✅ Your configured Maven version name
    }

    stages {
        stage('Compile') {
            steps {
                echo '🔧 Compiling source code...'
                sh 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running unit tests...'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo '📦 Packaging the application...'
                sh 'mvn package'
            }
        }

        stage('Install') {
            steps {
                echo '📂 Installing to local Maven repo...'
                sh 'mvn install'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully.'
        }
        failure {
            echo '❌ Build failed. Check the logs.'
        }
    }
}
