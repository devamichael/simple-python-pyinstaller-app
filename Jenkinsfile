pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'hello-world'
                }
            }
            steps {
                sh 'whoami' 
            }
        }
    }
}
