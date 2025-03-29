/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'maven:3.9.9-eclipse-temurin-21-alpine' } }
      environment{
        DEV='DEV'
        PROD='PROD'
      }
      stages {
        stage('build-dev') {
            steps {
                sh 'echo "iniciando ${DEV}"'
                sh ''' 
                    mvn --version
                    ls -lah
                ''' 
            }
        }
        stage('Sanity-Check'){
          steps{
            input "El ambiente de stage se ve bien?"
          }
        }
        stage('build-prod'){
          steps{
            sh 'echo "iniciando ${PROD}"'
          }
        }
      }
      post{
        always{
          echo 'Terminó el pipe'
        }
        success{
          echo 'Termino de manera exitosa'
        }
        failure{
          echo 'fracaso total'
        }
     }
}
