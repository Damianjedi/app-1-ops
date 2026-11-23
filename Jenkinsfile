pipeline {
    agent any

    parameters {
        booleanParam(
            name: 'DEPLOY',
            defaultValue: false,
            description: 'Czy wykonać etap wdrożenia?'
        )
    }

    stages {
        stage('Build') {
            steps {
                echo 'Rozpoczynam budowanie aplikacji...'
                // Kroki budowania
            }
        }

        stage('Test') {
            steps {
                echo 'Uruchamiam testy...'
                // Kroki testowania
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
                // Kroki wdrożenia
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
    }
}
