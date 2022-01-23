pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'alpine'
                    args '-v /tmp:/var/jenkins_home/workspace'
                }
            }
            steps {
                sh 'whoami' 
            }
        }
    }
}
