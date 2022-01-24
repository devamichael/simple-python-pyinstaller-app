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
            agent {
    kubernetes {
        label podlabel
        yaml """
kind: Pod
spec:
  containers:
  - name: flak8
    image: docker.io/alpine/flake8:4.0.1
    command:
    - /busybox/cat
    tty: true
  restartPolicy: Never
"""
   }
            steps {
                sh 'flake8 --ignore=E302,W503 sources/add2vals.py sources/calc.py' 
            }
        }
    }
}
