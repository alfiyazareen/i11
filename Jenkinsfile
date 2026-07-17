Pipeline{
    agent any{
        triggers{
           cron('H/2 * * * *')
        }
        stages{
           stage('checkout'){
               steps{
                  git ' '
               }
           }
           stage('Build'){
               steps{
                  sh 'mvn clea package'
               }
           }
           stage('Build Docker Image'){
               steps{
                  sh 'docker build-t java-demo'
               }
           }
           stage('Deploy'){
              steps{
                 sh 'kubectl deploy -f deployment.yaml'
                 sh 'kubectl deploy -f service.yaml'
              }
           }
        }
    }
}