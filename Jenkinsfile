pipeline{
	agent any;
	

tools{
	maven:'Maven'
	}

stages{
	stage('Checkout'){
		steps{
			git branch:'main', url:'https://github.com/Bankai043/LabTest-Immutable-.git'
		}
	}
	
	stage('Build'){
		steps{
			sh 'mvn clean package'
			}
		}
	
	stage('Test'){
		steps{
			sh 'mvn test';
			}
		}
	
	stage('Run Applcation'){
		steps{
			sh 'java -jar/target/GuavaMavenApp-1.0-SNAPSHOT.jar'	
			}
		}
		
	post{
	   success{
	       echo 'Build and Deployment complete'
	   }
	   failure{
	       echo 'Build failed'
	   }
	  }
	 }
}
