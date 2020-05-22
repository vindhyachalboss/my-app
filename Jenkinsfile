node{
	parameters { 
         string(name: 'tomcat_dev', defaultValue: '13.232.63.219', description: 'Staging Server')
         
    } 
stage('SCM Checkout'){ 
	git 'https://github.com/vindhyachalboss/my-app'  
   }  
   stage('Compile-Package'){
	   // Build using maven
	    def mvnHome = tool name: 'maven-3', type: 'maven'
	   sh "${mvnHome}/bin/mvn package "
   }
 stage('Deploy to Tomcat'){
      
     sh "scp -i /home/ec2-user/tomcat.pem  **/target/*.war ec2-user@${params.tomcat_dev}:/usr/share/tomcat8/webapps"
   }

}
