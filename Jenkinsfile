pipeline {
    agent { label 'jenkins-slave' }
    stages {
        stage ('SCM') {
            steps {
                checkout([$class: 'GitSCM', 
                	branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, 
                	extensions: [], 
                	submoduleCfg: [], 
                	userRemoteConfigs: [[url: 'https://github.com/Naresh240/Jenkins-Master-Slave.git']]])
            }
        }
        stage ('Build Artifact') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
