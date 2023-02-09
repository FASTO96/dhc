pipeline {
    agent {
        label 'myage'
    }      
    stages{
        stage('build') {
            steps {
                dob = docker.build("sab22/wapp")
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
