pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh 'python script.py'
            }
	}
	stage ('Check-Git-Secrets') {
      	    steps {
                sh 'rm trufflehog || true'
                sh 'trufflehog --json https://github.com/Rohitgarg253/temporary.git > trufflehog '
                sh 'cat trufflehog'
            }
        }
	stage('Testing Stage') {
            steps {
                sh 'python test.py'
            }
	}
	stage('Deployment Stage') {
            steps {
                sh 'python deploy.py'
            }
        }
	
      }
}
