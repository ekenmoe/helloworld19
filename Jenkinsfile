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
            }
        }
   stage("Deploy") {
            
            steps {
            echo 'Deploy the application......'
            }
        }
  
    }
    
}
