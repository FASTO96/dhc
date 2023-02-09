node {
    def dob

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       dob = docker.build("sab22/wapp")
    }


    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push("${env.BUILD_NUMBER}")
        }
    }
    

}
