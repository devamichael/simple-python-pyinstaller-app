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
                sh 'flake8 --ignore=E302,W503 sources/add2vals.py sources/calc.py' 
            }
        }
        stage('static-analysis') { 
            agent {
                docker {
                    image 'pylint'
                    args '--entrypoint='
                }
            }
            steps {
                sh 'cd sources && pylint --disable=C0103,C0116 add2vals.py calc.py' 
            }
        }
        stage('Build') { 
            agent {
                docker {
                    image 'python:3-alpine' 
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}
