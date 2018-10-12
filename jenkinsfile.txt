pipeline{
    agent any
	
	stages{
	   stage('Compile stage'){
	    
		  steps{
		      withMaven(maven : 'maven_3_5_0'){
			       sh 'mvn clean compile'
				}
			}
		}
		
       	stage('Testing stage'){
	    
		  steps{
		      withMaven(maven : 'maven_3_5_0'){
			       sh 'mvn clean test'
				}
			}
		}	
		stage('Deployment stage'){
	    
		  steps{
		      withMaven(maven : 'maven_3_5_0'){
			       sh 'mvn clean deploy'
				}
			}
		}
	}
}
	