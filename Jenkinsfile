pipeline {
agent {label "agentfarm" }
stages {
stage('Installing Maven') {
steps {
sh 'sudo apt update -y && sudo apt upgrade -y'
sh 'sudo apt install -y wget tree unzip maven'
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
