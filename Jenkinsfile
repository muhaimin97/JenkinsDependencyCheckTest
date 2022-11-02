pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git 'C:/Users/muhai/Downloads/Y3T1/ICT3103 Secure Software Devlopment/W6/LAB/OWASP Jenkins Repo/JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}