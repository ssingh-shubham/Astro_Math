pipeline {
    agent any

    stages {

        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Tool Install') {
            steps {
                echo 'Installing required tools if configured'
                // Example: sh 'npm install' if NodeJS or other tools are set up manually
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
            }
        }

        stage('Test') {
            steps {
                echo 'Run tests here if any'
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
