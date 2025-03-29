/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'maven:3.9.9-eclipse-temurin-21-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "iniciando"'
                sh ''' 
                    mvn --version
                    ls -lah
                ''' 
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
