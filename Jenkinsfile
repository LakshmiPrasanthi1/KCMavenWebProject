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
	   
      stage('Sonar') {
                    //add stage sonar
                    sh 'mvn sonar:sonar'
                }
       
}
