pipeline {
     agent any
environment {
    IMAGE_REPO = "hemanthhr/flaskhello"
    // Instead of hemanthhr, use your git username
}     
     stages {
         stage('Build Docker Image') {
              steps {

                  sh " docker image build -t  ${env.IMAGE_REPO}:${env.GIT_COMMIT} ."
              }
         }
         stage('Push Docker Image') {
              steps {
                  withDockerRegistry([url: "", credentialsId: "dockerhub"]) {
                      sh " docker image push ${env.IMAGE_REPO}:${env.GIT_COMMIT}"
                  }
              }
         } 
          stage('update helm chart values') {
              steps {
                  sh "ls"
              }
         }
             }
        }
