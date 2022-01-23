pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                docker {
                    image 'alpine/flake8:4.0.1'
                    args '--entrypoint='
                }
            }
            steps {
                sh 'flake8 --ignore=E302 sources/add2vals.py sources/calc.py' 
            }
        }
        stage('static-analysis') { 
            agent {
                docker {
                    image 'localhost:5000/pylint'
                    args '--entrypoint='
                }
            }
            steps {
                sh 'cd source && pylint sources/add2vals.py sources/calc.py' 
            }
        }
    }
}
