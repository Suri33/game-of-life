

  node 
    {
  
      stage ('SCM') 
	  {
	  git 'https://github.com/Suri33/game-of-life.git'
	  }
	  
	  stage ('Build packge') 
	  {
            sh 'mvn package'	  
	  }
	   
	   stage ('Artifacory')
	         {
             archiveArtifacts 'gameoflife-core/target/*.jar'             
			 }
	   
	        
		 stage ( 'Sonar Qube')
		 {

         withSonarQubeEnv ('SonarPlaying') 
		    {
		   
             sh ' mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'              
           
		   }					 
	   }
		 
}		 