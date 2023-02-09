pipeline {
    agent {
        label 'myage'
    }      
    stages{
        stage('build') {
            steps {
                dob = docker.build("sab22/wapp:1.0.2")
            }
        }
               
        
        stage('push') {
            steps {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub'){
                    dob.push()
                    
                }
                
            }
        }        
        
        
    }
}
