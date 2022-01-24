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
                sh 'echo "hello world"' 
            }
        }
    }
}
