pipeline {
    agent any

    stages {
	
	stage('Compile')
	{
	    steps{
           sh "git clone https://github.com/dheeraj17044/jenkinsdemo.git"
	       sh "mvn clean -f jenkinsdemo"	
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