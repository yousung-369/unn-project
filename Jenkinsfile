node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("unn-project/mynginxv9")
         
     }
     stage('Push image') {
         docker.withRegistry('https://ec2-43-202-37-66.ap-northeast-2.compute.amazonaws.com/',  'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
