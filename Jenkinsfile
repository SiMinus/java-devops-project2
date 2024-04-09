pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '9629ff56-005a-43e2-acdd-20db18e4eff1', 
                path: '', 
                url: 'http://ec2-18-169-18-113.eu-west-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
        }
    }
}
