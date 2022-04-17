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
	bat 'mvn clean test'
	}
	}
	 
	stage('Deploy Application'){
	steps{
	bat 'mvn clean deploy -DmuleDeploy -DskipTests -Dmule.version=4.4.0 -Danypoint.username=Prajwal16 -Danypoint.password=Magenta2022$# -Denv=Sandbox -Dappname=jenkins-demo-pipeline-1 -DvCore=Micro -Dworkers=1'
	 }
	 }
  }
  
   post {
    success {
    	message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
    	body: "", to: "disguisedfox74gmail.com"
    }
    failure {
        subject: "Failed Pipeline: ${currentBuild.fullDisplayName}."
        body: "Something is wrong with ${env.BUILD_URL}. Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", to: "disguisedfox74gmail.com"
    }
}  
}   