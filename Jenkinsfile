pipeline {
	environment {
		helloWorld = "Hi!"
	}
	agent {
		agent any
	}
	options {
		timeout(time: 1, unit: 'HOURS')
	}
	stages {
		stage ('preparation') {
			steps {
				deleteDir()
			}
		}
		stage ('helloWorld') {
			steps {
				echo "${helloWorld}"
			}
		}
	}
}