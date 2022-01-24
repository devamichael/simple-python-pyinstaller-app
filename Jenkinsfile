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
    command:
    - cat
    tty: true
"""
                }
            }
            steps {
                container('flake8') {
                    sh 'flake8 --ignore=E302 sources/add2vals.py sources/calc.py' 
                }
            }
        }
    }
}
