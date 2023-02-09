pipeline {
    environment{
      apl = ""
    }
    agent {
        label 'myage'
    }

    stages {
            stage('clone') {
            steps {
                scm checkout
            }
        }
        
        stage('build') {
            steps {
                apl = docker.build("sab22/wapp:1.0.7")
            }
        }        

        stage('push') {
            steps {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                   apl.push()
            }
                
            }
        }        
        
    }
}
