pipeline {
	environment {
		project = "https://github.com/fe6865d3bf/juice-shop.git!"
    containerName = "Magazin sokov"
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
		stage ('get src') {
			steps {
				git url: "${project}"
			}
		}
    stage ('get dependency') {
      steps {
        echo 'npm install'
      }
    }
    stage ('run test') {
      parallel {
        stage ('run unit') {
          steps {
            echo 'units'
          }
        }
        stage ('run lints') {
          steps {
            echo 'lints'
          }
        }
      }
    }
    stage ('build') {
      steps {
        script {
          dockerImage = docker.build("${containerName}", ".")
        }
      }
    }
	}
}