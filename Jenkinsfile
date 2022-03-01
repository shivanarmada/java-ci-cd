pipeline{
    agent any 
    stages{
        stage("sonarquality check"){
            agent {
                docker {
                    image "openjdk:11"
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                             sh 'chmod +x gradlew'
                             
                    }
                    timeout(time: 1, unit: 'HOURS') {
                      def qg = waitForQualityGate()
                      if (qg.status != 'OK') {
                           error "Pipeline aborted due to quality gate failure: ${qg.status}"
                      }
                    }
                }

            }
        }
    }
}