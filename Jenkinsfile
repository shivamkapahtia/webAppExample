pipeline {
    agent any
    stages {
        stage("Maven version") {
            steps {
                sh "mvn --version"
            }
        }   
        stage("Clone the GIT Project") {
            steps {
                git "https://github.com/kishancs2020/webAppExample.git"
            }
        }    
        stage("Clean the project") {
            steps {
                sh "mvn clean"
            }
        }
        stage("Test project") {
            steps {
                sh "mvn test"
            }
        }
        stage("make package") {
            steps {
                sh "mvn package"
            }
        }
        stage("Deploy on tomcat"){
            steps {
                sh "deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://74.235.140.25:8080/')], contextPath: null, war: '**/*.war'"
            }
        }        
    }  
}
