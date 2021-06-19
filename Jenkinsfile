pipeline {
    agent any

    stages {
      stage(' revisión SAST') {
           steps{
               echo '========================================='
              echo '                SONARQUBE '
              echo '========================================='
                script {                  
                    def scannerHome = tool 'SonarQube Scanner';//def scannerHome = tool name: 'SonarQube Scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv('Sonar Server') {
                      sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=tarea4-devsecops -Dsonar.host.url=http://localhost:9000 -Dsonar.login=9743ddf70305abcb1122232427f768952c92c006"
                    }
                }
           }
        }
    }
}
