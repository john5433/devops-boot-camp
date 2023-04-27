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
stage('Deploying Application') {
 steps {
    script{
   withEnv(['JENKINS_NODE_COOKIE=dontkill']) {
sh 'nohup java -jar ./target/springboot-bootcamp-0.0.1-SNAPSHOT.jar &'
}
}
}
}
}
}
