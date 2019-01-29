#!groovy

node {
       stage('Checkout'){
          git credentialsId: 'automatejob', url: 'https://github.com/LakshmiPrasanthi1/KCMavenWebProject.git'
          
       }

       stage('Compiling'){
	
      // Get maven home path
      def mvnHome =  tool name: 'M2_HOME', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   
          
       }
	
	stage(‘Deploy-To-Tomcat’){

	 
	if('${env.BUILD_URL}' == 'master'){
           sshagent([‘tomcat’]) {
           sh ‘scp -o StrictHostKeyChecking=no target/*.war ec2-user@10.10.2.254:/opt/apache-tomcat-8.0.53/webapps’
     }
	 }
	 
  }
   
	   
      //stage('Sonar') {
                    //add stage sonar
                    //sh 'mvn sonar:sonar'
               // }
       
}
