pipeline {
    agent any  // Run on any available Jenkins agent

    environment {
        // Optional: set Maven home if not in PATH
        // MAVEN_HOME = '/opt/apache-maven-3.9.4'
        // PATH = "${env.MAVEN_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull code from GitHub
                git branch: 'main', url: 'https://github.com/peterduong/CucumberBasics.git'
            }
        }

        stage('Build & Verify') {
            steps {
                // Run Maven verify
                sh 'mvn verify'
            }
        }
    }

    post {
        success {
            echo 'Build and tests passed!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
