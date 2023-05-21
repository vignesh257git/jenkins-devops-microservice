//Scripted
//Declarative
pipeline {
    agent any
	// agent { docker { image 'maven:3.6.3'} }
	// agent { docker { image 'node:20-alpine3.16'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = '$dockerHome/bin:$mavenHome/bin:$PATH'
	}
    stages {
        stage('Build'){
			steps {
			    sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH: - $PATH"
				echo "BUILD NO: - $env.BUILD_NUMBER"
				echo "BUILD ID: - $env.BUILD_ID"
				echo "JOB NAME: - $env.JOB_NAME"
				echo "BUILD TAG: - $env.BUILD_TAG"
				echo "BUILD URL: - $env.BUILD_URL"

			}
	    }
	    stage('Test'){
			steps {
				echo "Test"
			}
	    }
	    stage('Integration Test'){
			steps {
				echo "Integration Test"
			}
	    }
    }

	post {
		always {
			echo "I run always"
		}
		success {
			echo "I run during success"
		}
		failure {
			echo "I run during failure"
		}
		unstable {
			echo "I run when things are unstable"
		}
		changed {
			echo "I run when the status of build is changed"
		}
	}
}