pipeline {

    agent any

	environment {
		dockerImage = ''
		registry = "dheeraj17044/demo-$BUILD_NUMBER"
		registryCredential= 'docker_cred'
			}

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
		
		stage('Building Our Image') {
			steps {
				script{
						dockerImage=docker.build(registry)
						}
					}
			}
			
		stage('Deploy our image') {
			steps {
				script {
						docker.withRegistry( '', registryCredential ) {
							dockerImage.push()
							}
						}
					}
			}
	
		stage('Cleaning up') {
			steps {
					bat "docker rmi $registry"
					}
				}
		}
	}
	}
}