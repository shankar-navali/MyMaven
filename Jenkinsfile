pipeline{
	agent any
	
	tools{
	   maven 'Maven'
	   }
	stages{
	    stage('Checkout'){
	    	steps{
		   git branch: 'master', url:'https://github.com/shankar-navali/MyMaven.git'
		   }
		}
	    stage('Build'){
	    	steps{
	    	   sh 'mvn clean package'
	    	   }
	    }
	    
	    stage('Test'){
	    	steps{
	    	   sh 'mvn test'
	    	   }
	    }
	    
	    stage('Runnn Application'){
	    	steps{
	    	  sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
	    	  }
	    }
	  }
	  
	  post{
	     success{
		echo 'Build successfully'
		}
	     failure{
		echo 'failed Build'
		}
	}
}
