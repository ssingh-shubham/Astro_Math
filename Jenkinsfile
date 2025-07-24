pipeline {
    agent any

    tools {
        // Add tool installation if needed (e.g., Maven, NodeJS)
        // nodejs 'NodeJS_18' // Uncomment if NodeJS tool is configured in Jenkins
    }

    stages {

        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Tool Install') {
            steps {
                echo 'Tools like NodeJS, Maven can be automatically installed via Jenkins toolchains'
                // Example if using Node
                // sh 'npm install'
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
                // Or run any frontend build tools if applicable, e.g., npm run build
            }
        }

        stage('Test') {
            steps {
                echo 'Run frontend or backend tests here'
                // For example:
                // sh 'npm test'
            }
        }

        stage('Docker Build Application') {
            steps {
                script {
                    docker.build('astro-math:latest')
                }
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
