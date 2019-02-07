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
     scp '/root/.jenkins/workspace/scriptpip/webapp/target/webapp.war ubuntu@172.31.20.70:/var/lib/tomcat7/webapps/qa1.war'
   }
   stage('continuous testing')
   {
      git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
      sh 'java -jar testing.jar'
   }
   stage('continuous deployment')
   {
     scp '/root/.jenkins/workspace/scriptpip/webapp/target/webapp.war ubuntu@172.31.22.148:/var/lib/tomcat7/webapps/pro1.war'

   }
}



