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
	bat 'mvn deploy -DmuleDeploy -DskipTests -Dmule.version=4.4.0 -Danypoint.username=Prajwal16 -Danypoint.password=Magenta2022$# -Denv=Sandbox -Dappname=jenkins-demo-pipeline-1 -DvCore=Micro -Dworkers=1 -Dbusiness.group=T-Systems\MuleSoft Enablement T-Systems'
	 }
	 }
  }
}   