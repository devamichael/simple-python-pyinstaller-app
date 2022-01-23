pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'alpine/flake8:4.0.1'
                    args '-v /tmp:/var/jenkins_home/workspace'
                }
            }
            steps {
                sh 'whoami' 
            }
        }
    }
}
