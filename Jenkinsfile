pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'alpine/flake8:4.0.1'
                    args  '--volumes-from da6dc95e2e7207f230436e8fc9e5f40bea7b6e04a62fcb88465424f71026bfb0'
                }
            }
            steps {
                sh 'flake8 sources/add2vals.py sources/calc.py' 
            }
        }
    }
}
