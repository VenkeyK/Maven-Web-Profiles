#!groovy

pipeline {
agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '4174c105-8ecc-47de-bebb-74b38b3136ad', url: 'https://github.com/VenkeyK/Maven-Web-Profiles.git']]])
            }
        }
        stage('Build and Test') {
            steps {
               //withEnv(["PATH=${tool 'apache-maven-3.6.0'}/bin:${tool 'java-1.8.0-openjdk-amd64'}/bin:${env.PATH}"])
                bat 'mvn clean install'
            }
        }
        stage('Deploy') {
            steps {
              // sh 'scp /var/lib/jenkins/workspace/pipe/target/*.war ubuntu@18.212.8.72:/opt/tomcat/apache-tomcat-8.5.37/webapps/'
              // sh 'cp /var/lib/jenkins/workspace/pipe1/target/*.war /opt/tomcat/apache-tomcat-8.5.37/webapps/'
            }
        }
    }
}
