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
    	body: mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "disguisedfox74@gmail.com"
    }
    failure {
        subject: "Failed Pipeline: ${currentBuild.fullDisplayName}."
        body: "Something is wrong with ${env.BUILD_URL}. <b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "disguisedfox74@gmail.com"
    }
}  
}   