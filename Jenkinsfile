pipeline {
    agent any

    tools {
        // Define tools if needed, e.g., NodeJS, Maven
        // nodejs 'NodeJS_18' // Uncomment if configured in Jenkins
    }

    stages {

        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Tool Install') {
            steps {
                echo 'Installing required tools if configured'
                // Example: sh 'npm install'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ssingh-shubham/Astro_Math/'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for HTML/CSS/JS'
                // Or use: sh 'npm run build' if applicable
            }
        }

        stage('Test') {
            steps {
                echo 'Run tests here if any'
                // Example: sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp -r * /var/www/html/'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
        always {
            echo 'Pipeline finished.'
        }
    }
}
