node{
	
stage('SCM Checkout'){ 
	git 'https://github.com/vindhyachalboss/my-app'  
   }  
   stage('Compile-Package'){
	   // Build using maven
	    def mvnHome = tool name: 'maven-3', type: 'maven'
	   sh "${mvnHome}/bin/mvn package "
   }
stage('Deploy to Tomcat'){
      
      sshagent(['a6d59768-f54d-40cb-990c-8e3cf31fc258']) {
         sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.32.91:/usr/share/tomcat8/webapps'
      }
   }
	

}
