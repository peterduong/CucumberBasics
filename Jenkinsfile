pipeline {
    agent any  // Run on any available Jenkins agent

   

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
