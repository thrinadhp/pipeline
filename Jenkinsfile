node('master')
{
  stage('continuous download')
    { 
        git 'https://github.com/thrinadhp/maven.git'
     }
   stage('continuous build')
   {
      sh 'mvn package'
   }
   stage('continuous deployment')
   {
     sh 'scp /root/.jenkins/workspace/scriptpip/webapp/target/webapp.war ubuntu@172.31.20.70:/var/lib/tomcat7/webapps/qa2.war'
   }
   stage('continuous testing')
   {
      git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
      sh 'java -jar testing.jar'
   }
   stage('continuous delivery')
   {
     input message: 'Requesting for approval from DM', submitter: 'kumar'
     sh 'scp /root/.jenkins/workspace/scriptpip/webapp/target/webapp.war ubuntu@172.31.22.148:/var/lib/tomcat7/webapps/pro2.war'

   }
}



