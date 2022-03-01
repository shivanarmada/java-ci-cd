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
                    withSonarQubeEnv(credentialsId: 'sonartoken') {
                             sh 'chmod +x gradlew'
                             sh './gradlew sonarqube'
                    }
                }

            }
        }
    }


}
