pipeline {
    agent any

    stages {
	
	stage('Compile')
	{
	    steps{
           echo env.GIT_BRANCH
	       sh '''chmod 777 mvnw 
		    ./mvnw clean compile '''	
		}
	}
	
	stage('Test')
	{
		steps{
			sh '''
		    ./mvnw test'''	
		}
	}

	stage('Create JAR') {

		steps {
			sh '''
		    	./mvnw install'''	
		}
	}
	}
}