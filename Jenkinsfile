pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'flake8:4.0.1' 
                }
            }
            steps {
                sh 'flake8 sources/add2vals.py sources/calc.py' 
            }
        }
    }
}