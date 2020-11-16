pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }
        
        stage("Deploy"){
            steps{
               deploy adapters: [tomcat7(credentialsId: 'e67731c3-4b9b-4218-a813-12c7f6732e32', path: '', 
               url: 'http://ec2-3-139-233-238.us-east-2.compute.amazonaws.com:8080/')],
               contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
