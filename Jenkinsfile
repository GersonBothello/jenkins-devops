
node {
	echo "Build"
	echo "Test"
}

//Declarative
pipeline {
	agent any
	stages {
		stage ('Build') {
			steps{
				echo("build")
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
}
