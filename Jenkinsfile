pipeline{
    agent any 
    stages{
        stage("sonarquality check"){
            agent {
                docker {
                    image "openjdk:11"
                }
            }
            stage ('Exec Gradle') {
           steps {
             rtGradleRun (
             tasks: 'build',
             tool: 'Gradle_Home', // Tool name from Jenkins configuration
             rootDir: "/var/lib/jenkins/workspace/java-gradle",
             sh 'chmod +x gradlew'
             sh './gradlew sonarqube'
             )
            }
        }
                    }
                    
                }

            }
        }
    }
}