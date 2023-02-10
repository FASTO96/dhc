node {
    def dob
    agent {
        label 'myage'
    }
    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       dob = docker.build("sab22/wapp:1.0.9")
    }


    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            sh "docker push sab22/wapp:1.0.8"
            dob.push()
        }
    }
    

}
