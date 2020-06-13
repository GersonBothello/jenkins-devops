
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
		PATH="$dockerHome/bin:$mavenHome/bin"
	}
	

	stages {
		stage ('Build') {
			steps{
				//echo("build")
				echo("path - $PATH")
			}
		}
		stage ('Test') {
			steps{
				echo("Test")
			}
		}
		stage ('Integration Testing') {
			steps{
				echo("build")
			}
		}
	}
	post{
			always{
				echo("I am done")
			}
		}
}
