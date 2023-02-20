pipeline {
       agent {label  "agentfarm" }
       stages {
              stage('Installing Maven'){
           steps {
               sh 'sudo apt-get update -y && sudo apt-get upgrade -y'
               sh 'sudo apt install -y wget tree unzip openjdk-11-jdk maven'
           }
       	  }

             stage('Second-Stage') {
                    steps {
                           echo 'This is Second-stage'
                    }
              }
             stage('Third-Stage') {
                    steps {
                           echo 'This is Third-stage'
                    }
              }
        }
   }

