pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/ssingh-shubham/Astro_Math/'
            }
        }
        stage('Build') {
            steps {
                echo 'No build needed for HTML/CSS/JS'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp -r * /var/www/html/'
            }
        }
    }
}
