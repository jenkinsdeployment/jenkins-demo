pipeline
  {
   agent any
    environment {
            EMAIL_INFORM = 'disguisedfox74@gmail.com;pwankhade421@gmail.com'
        }
   stages{
	stage('Build Application'){
	steps{
	bat 'mvn clean install'
	}
	}
	 
	stage('Munit Test Application'){
	steps{
	bat 'mvn clean test'
	}
	}
	 
	stage('Deploy Application'){
	steps{
	bat 'mvn cle deploy -DmuleDeploy -DskipTests -Dmule.version=4.4.0 -Danypoint.username=Prajwal16 -Danypoint.password=Magenta2022$# -Denv=Sandbox -Dappname=jenkins-demo-pipeline-1 -DvCore=Micro -Dworkers=1'
	 }
	 }
  }
  
   post {
    success {
        mail to: 'disguisedfox74@gmail.com',
             subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
             body: "Deployment Successful ${env.BUILD_URL}"
    }
    failure {
        mail to: "${EMAIL_INFORM}",
             subject: "Pipeline failed: ${currentBuild.fullDisplayName}",
             body: "Deployment failed ${env.BUILD_URL}"
   } 
}  
}