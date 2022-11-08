pipeline {
    agent {
        dockerfile {
	    label 'docker'	
            //filename 'my.dockerfile' // Uncomment and change
        }
    }
    stages {
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
                sh '''python3 -m pytest -v --junitxml=junit.xml --cov-report xml --cov  adder.py'
                '''
	     }
	}
	stage('Hello Github') {
	    steps {
		echo "Hello Github!"
		
            }
	}
   post {
	always {
	    junit 'junit.xml'
	    cobertura coberturaReportFile: 'coverage.xml'
        }
   }
}
