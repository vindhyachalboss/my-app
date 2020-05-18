node{
stage('SCM Checkout'){ 
	url: 'https://github.com/vindhyachalboss/my-app'  
   }  
   stage('Compile-Package'){
	   // Build using maven
	    def mvnHome = tool name: 'maven-3', type: 'maven'
	   sh "${mvnHome}/bin/mvn "
   }
}
