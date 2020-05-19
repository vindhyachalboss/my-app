node{
stage('SCM Checkout'){ 
	git 'https://github.com/vindhyachalboss/my-app'  
   }  
   stage('Compile-Package'){
	   // Build using maven
	    def mvnHome = tool name: 'maven-3', type: 'maven'
	   sh "${mvnHome}/bin/mvn package "
   }
  stage('SonarQube Analysis') {
        def mvnHome =  tool name: 'maven-3', type: 'maven'
        withSonarQubeEnv('sonar-6') { 
          sh "${mvnHome}/bin/mvn sonar:sonar"
        }
    }
}
