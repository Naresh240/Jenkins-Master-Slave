pipeline {
    agent { label 'jenkins-slave' }
	  environment {
		  registry = 'naresh240/springboot-k8s:latest'
		  registryCredentials = 'docker-credentials'
		  dockerImage = ''
	  }
    stages {
        stage ('SCM') {
            steps {
                checkout([$class: 'GitSCM', 
                	branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, 
                	extensions: [], 
                	submoduleCfg: [], 
                	userRemoteConfigs: [[url: 'https://github.com/Naresh240/minikube-springbootCICD.git']]])
            }
        }
        stage ('Build Artifact') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
