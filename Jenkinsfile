pipeline {
    agent any

    stages {
        stage('Cloner le dépôt') {
            steps {
                git branch: 'main', url: 'https://github.com/Sionra/diginamic_jenkins.git'
            }
        }

        stage('Copier index.html') {
            steps {
                bat '''
                    if not exist C:\\www\\html mkdir C:\\www\\html
                    copy index.html C:\\www\\html\\index.html /Y
                '''
            }
        }

        stage('Afficher un message') {
            steps {
                echo 'Déploiement de index.html terminé.'
            }
        }
    }

    post {
        success {
            echo '✅ Déploiement réussi.'
        }
        failure {
            echo '❌ Une erreur est survenue.'
        }
    }
}