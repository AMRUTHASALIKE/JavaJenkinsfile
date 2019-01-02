@Library('SL1')_

pipeline
{
   agent any
   environment
   {
       deploy_user='ubuntu'
       ip='52.47.190.123'
       key='rs1'
       gitURL='https://github.com/AMRUTHASALIKE/JavaSample.git'
   }
   /*
   agent 
    {
        //label 'ubuntu'
        label 'master'
    }*/
    
   /* stage('Pull')
    {
       git 'https://github.com/AMRUTHASALIKE/JavaSample.git'
    }*/
    stages
    {
          stage('Welcome') 
   {
     //sh 'user=$BUILD_USER'
      
       steps
        {
     script
     {
     echo 'Hello'
        echo $deploy_user
     welcomeMsg deploy_user
     }
        }
   }
    stage('Build')
    {
       steps
        {
       sh 'pwd'
       dir('SpringMVCSecurityXML') 
       {
            // some block
            sh 'pwd'
            sh 'mvn clean install'
            sh 'touch file1'
       }
       sh 'pwd'
        }
    }
    stage('Deploy')
    {
        steps
        {
        dir('SpringMVCSecurityXML/target') 
       {
            // some block
            sh 'sudo cp SpringMVCSecurityXML.war /var/lib/tomcat8/webapps'
       }
        }
    }
    }
}
