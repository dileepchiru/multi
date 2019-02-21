node('master') 
{
   stage('Contnuous Download') 
   {
      git 'https://github.com/dileepchiru/multi.git'
   }
   stage('continuouss Build') 
   {
      sh label: '', script: 'mvn package'
   }
   stage('ContinuousDeployment') 
   {
       sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.24.58:/var/lib/tomcat7/webapps/qaenv.war'
   }
   stage('ContinuousTesting')
   {
       git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
   }
   stage('ContinuousDelivery')
   {
       sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.35.205:/var/lib/tomcat7/webapps/prodenv.war'
   }
   
   
   
   
   
   
   
   
   
   
   
}
