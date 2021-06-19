pipeline {
    agent any

    tools {
        maven 'Maven'
        nodejs "NodeJs"
    }

    stages {
      stage(' revisión SAST') {
           steps{
               echo '========================================='
              echo '                SONARQUBE '
              echo '========================================='
                script {
                    def scannerHome = tool 'SonarQube Scanner';//def scannerHome = tool name: 'SonarQube Scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv('Sonar Server') {
                      sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=Ms-Maven -Dsonar.sources=target/ -Dsonar.host.url=http://172.18.0.3:9000 -Dsonar.login=14c09fa032024d6f0e5923c7cead79f0bcaa23f3"
                    }
                }
           }
        }
    }
}
