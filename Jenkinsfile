node {
    def fap

        stage('clone') {

                checkout scm

        }
        stage('build') {

                fap = docker.build("sab22/wapp:1.0.7")

        }
        
        stage('push') {

                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') 
                {
                    fap.push()
                }

        }

}
