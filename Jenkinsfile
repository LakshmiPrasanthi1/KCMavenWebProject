#!groovy

node {
       stage('Checkout'){
          git credentialsId: 'automatejob', url: 'https://github.com/LakshmiPrasanthi1/KCMavenWebProject.git'
          
       }

       stage('Compiling'){

          sh 'mvn deploy'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                    sh 'mvn sonar:sonar'
                }
       
}
