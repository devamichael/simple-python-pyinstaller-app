pipeline {
    agent none 
    stages {
        stage('enforce-formatting') { 
            agent {
                kubernetes {
                    yaml """
kind: Pod
spec:
  containers:
  - name: flake8
    image: docker.io/alpine/flake8:4.0.1
    tty: true
"""
                }
            }
            steps {
                sh 'flake8 --ignore=E302,W503 sources/add2vals.py sources/calc.py' 
            }
        }
    }
}
