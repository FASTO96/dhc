node {
    def fap

        stage('clone') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                fap = docker.build("sab22/wapp:1.0.7")
            }
        }
        
        stage('push') {
            steps {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') 
                {
                    fap.push()
                }
            }
        }

}
