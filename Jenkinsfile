pipeline{
    agent any
    options{
        buildDiscarder(logRotator(numToKeepStr: '5', daysToKeepStr: '5'))
        timestamps()
    }
    environment{
        
        registry = "frontend/dev"
        registryCredential = '<dockerhub-credential-name>'        
    }
    
    stages{
        stage('Initialize'){
         def dockerHome = tool 'myDocker'
         env.PATH = "${dockerHome}/bin:${env.PATH}"
        }
       stage('Building image') {
         steps{
          script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
         }
       }
    }
//        stage('Deploy Image') {
//       steps{
//          script {
//             docker.withRegistry( '', registryCredential ) {
//             dockerImage.push()
//           }
//         }
//       }
    }
}
