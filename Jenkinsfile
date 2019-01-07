 node{
     stage('SCM'){
	 
	     git 'https://github.com/devopsram/jpetstore-6.git'

	 }
	 stage('Build the packages'){
	 
	    bat 'mvn package'

	 }
	 stage('Archieve the build'){
	     archive 'target/*.jar'
	 }
	 stage('Junit test results'){
	     junit 'target/surefire-reports/*.xml'
	 }
	 stage('Sonar qube analysis'){
	   
	   withSonarQubeEnv('sonarqube'){
	   
	         sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
	   }
	 
	 }
    
 
}