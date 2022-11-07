pipeline {
    agent {
        dockerfile {
            label 'docker'
            label 'python:3'
        }
    }
        stage('Compile') {
            steps {
                sh 'python3 -m compileall adder.py'
            }
        }
        stage('Run') {
            steps {
                sh 'python3 adder.py 3 5'
            }
        }
        stage('Unit test') {
            steps {
                sh 'python3 -m unittest adder.py'
            }
        }
}
