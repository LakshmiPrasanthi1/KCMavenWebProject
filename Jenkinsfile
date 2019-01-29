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
           
           sh 'cp mypipelinePrj/target/maven-web-project-1.0-SNAPSHOT.war E:/DevOps/Softwares/apache-tomcat-8.5.37webapps/'
     
	 }
	 
  
   
	   
      //stage('Sonar') {
                    //add stage sonar
                    //sh 'mvn sonar:sonar'
               // }
       
}
