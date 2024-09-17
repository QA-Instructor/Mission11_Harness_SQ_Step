pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'git branch: 'main', url: 'https://github.com/huskyrat/lbg-vat-calculator'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonarqube-student4') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}

