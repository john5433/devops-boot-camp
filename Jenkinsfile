pipeline {
       agent {label  "agentfarm" }
       stages {
              stage('Installing Maven'){
           steps {
               sh 'sudo apt-get update -y && sudo apt-get upgrade -y'
               sh 'sudo apt install -y wget tree unzip openjdk-11-jdk maven'
           }
       	  }

             stage('Compiling and Running Test Cases') {
         steps {
              sh 'mvn clean'
              sh 'mvn compile'
              sh 'mvn test'
       }
   }

             stage('Creating Package') {
                 steps {
           	   sh 'mvn package'
       }
     }

      }
   }

