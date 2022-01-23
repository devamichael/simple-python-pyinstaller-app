pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'alpine/flake8:4.0.1'
                    args  '-v /var/jenkins_home/workspace/:/var/jenkins_home/workspace/'
                }
            }
            steps {
                sh 'flake8 sources/add2vals.py sources/calc.py' 
            }
        }
    }
}
