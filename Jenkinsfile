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
                                sh 'chmod 777 gradlew'
                                sh './gradlew sonarqube'
                    }
                    
                }

            }
        }
    }
}