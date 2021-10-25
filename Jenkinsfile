pipeline {
    agent any

    stages {
	
	stage('Compile')
	{
	    steps{
	       bat "mvn clean -f jenkinsdemo"	
		}
	}
	
	stage('Test')
	{
		steps{
			bat '''
		    ./mvnw test'''	
		}
	}

	stage('Create JAR') {

		steps {
			bat '''
		    	./mvnw install'''	
		}
	}
	}
}