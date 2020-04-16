pipeline {
    
    agent any 
    
    tools {
    maven 'M2_HOME'
    }
    
    stages {
        
        stage("Build") {
            
            steps {
                echo 'Building the application.....'
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
                
            }
        }
        
        stage("Test") {
            
            steps {
                
            echo 'Testing the application......'
                sh 'mvn test'
            }
        }
   stage("Deploy") {
            
            steps {
                echo 'deploying the application......'
                deploy adapters: [tomcat8(credentialsId: 'TomcatID', path: '', url: 'http://34.228.39.56:8080/')], contextPath: null, war: '**/*.war'
            }
        }
  
    }
    
}
