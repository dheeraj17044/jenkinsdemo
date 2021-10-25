pipeline {
    agent any

    stages {
	
	stage('Compile')
	{
	    steps{
           bat "git clone https://github.com/dheeraj17044/jenkinsdemo.git"
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