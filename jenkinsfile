pipeline{
    tools{
        jdk 'Java'
        maven 'Maven'
    }
    agent none
    stages{
     stage('compile'){
         agent any
         steps{
             sh 'mvn compile'
         }
     }
     stage('test'){
         agent any
         steps{
             sh 'mvn test'
         }
         POST{
             always{
                 junit 'gameoflife-web\target\surefire-reports\*.xml'
             }
         }
     }
     stage('package'){
         agent any
         steps{
             sh 'mvn package'
         }
     }   
    }
}
