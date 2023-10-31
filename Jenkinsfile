pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                git branch: "main", url: "https://github.com/ailis-mc/lbg-vat-calculator/tree/main"

            }
        }
        stage("SonarQube Analysis") {
            environment {
                scannerHome = tool 'sonarqube'
            }
            steps {
                withSonarQubeEnv("sonar-qube-ailis") {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}