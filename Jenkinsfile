pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'alpine/flake8:4.0.1'
                }
            }
            steps {
                sh 'whoami' 
            }
        }
    }
}
