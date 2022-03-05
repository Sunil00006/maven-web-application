node{
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])

def mavenHome =tool name: "maven3.8.3"

stage('Checkoutcode'){

git branch: 'development', credentialsId: '36ac0f08-10db-4458-901f-de9317377693', url: 'https://github.com/Sunil00006/maven-web-application.git'
}

stage('build'){
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactIntoNexusRepo'){
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppintoTomcatserver')
{
sshagent(['6dcb3576-7531-429b-afdb-ce5b0c7f0583']) {
  sh "scp -o StrictHostkeyChecking=no target/maven-web-application.war ec2-user@13.232.172.96:/opt/apache-tomcat-9.0.58/webapps/"  
}
}
*/
}
