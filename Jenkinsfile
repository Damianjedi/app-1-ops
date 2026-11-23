
pipeline {
    agent any

    parameters {
        booleanParam(
            name: 'DEPLOY',
            defaultValue: false,
            description: 'Czy wykonać wdrożenie aplikacji?'
        )
    }

    stages {

        stage('Git Checkout') {
            steps {
                echo 'Pobieranie kodu źródłowego z repozytorium Git...'

                git branch: 'main',
                    url: 'https://github.com/PeterPorzuczek/TimeRiddle.git'

                echo 'Kod źródłowy został pobrany.'
            }
        }

        stage('Build') {
            steps {
                echo 'Rozpoczynam budowanie aplikacji...'

                // Tutaj dodaj polecenia budowania aplikacji
            }
        }

        stage('Test') {
            steps {
                echo 'Uruchamiam testy aplikacji...'

                // Tutaj dodaj polecenia testowania aplikacji
            }
        }

        stage('Deploy') {
            when {
                expression {
                    return params.DEPLOY == true
                }
            }

            steps {
                echo 'Rozpoczynam wdrażanie aplikacji...'

                // Tutaj dodaj polecenia wdrażania aplikacji
            }
        }
    }

    post {
        success {
            echo 'Pipeline zakończony pomyślnie!'
        }

        failure {
            echo 'Wystąpił błąd podczas wykonywania pipeline!'
        }

        always {
            echo 'Zakończono wykonywanie Pipeline.'
        }
    }
}
