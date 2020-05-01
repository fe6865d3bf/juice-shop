pipeline {
	environment {
		helloWorld = "Hi!"
	}
	agent any
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