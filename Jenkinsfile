pipeline {
    agent any

    stages {
	
	stage('Compile')
	{
	    steps{
	       bat "mvn clean compile"	
		}
	}
	
	stage('Test')
	{
		steps{
			bat "mvn test"	
		}
	}

	stage('Create JAR') {

		steps {
			bat "mvn install"	
		}
	}
	}
}