node {
    def dob

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       dob = docker.build("sab22/wapp:1.0.6")
    }


    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push()
        }
    }
    

}
