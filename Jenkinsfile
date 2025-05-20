pipeline {
    agent any

    stages {
        stage('Copier index.html') {
            steps {
                bat 'copy index.html /var/www/html/index.html'
            }
        }

        stage('Redémarrer Apache2') {
            steps {
                sh 'sudo systemctl restart apache2'
            }
        }
    }

    post {
        success {
            echo 'Déploiement HTML effectué et Apache redémarré.'
        }
        failure {
            echo 'Une erreur est survenue pendant le déploiement.'
        }
    }
}
 