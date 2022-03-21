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
	bat 'mvn deploy -DmuleDeploy -DskipTests -Dmule.version=4.4.0 -Danypoint.username=PSW1 -Danypoint.password=Pr@jw@l16 -Denv=Sandbox -Dappname=jenkins-demo-pipeline -DvCore=Micro -Dworkers=1'
	 }
	 }
  }
}   