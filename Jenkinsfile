pipeline
  {
   agent any
   stages{
	stage('Build Application'){
	steps{
	bat 'mvn clean install'
	}
	}
	 
	stage('Munit Test Application'){
	steps{
	bat 'mvn test'
	}
	}
	 
	stage('Deploy Application'){
	steps{
	bat 'mvn package deploy -DmuleDeploy'
	 }
	 }
  }
}   