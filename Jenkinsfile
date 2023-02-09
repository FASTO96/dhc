pipeline {
    agent {
        label 'myage'
    }      
        
        stage('build') {
            steps {
                dob = docker.build("docker build -t sab22/wapp:1.0.2")
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
