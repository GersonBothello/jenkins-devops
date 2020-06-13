
node {
	echo "Build"
	echo "Test"
}

//Declarative
pipeline {
	agent any

	
	environment {
		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	

	stages {
		stage ('Checkout')
			steps{
				sh 'docker version'
				sh 'mvn --version' 
				//echo("build")
				echo("path - $PATH")
			}
		stage ('Compile') {
			steps{
				sh 'mvn clean compile' 
				echo("path - $PATH")
			}
		}
		stage ('Test') {
			steps{
				sh 'mvn test' 
				echo("Test")
			}
		}
		stage ('Integration Testing') {
			steps{
				echo("build")
				sh 'mvn failsafe:integration-test failsafe:verify' 
			}
		}
	}
	post{
			always{
				echo("I am done")
			}
		}
}
