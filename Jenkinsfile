pipeline {
    
    agent any 
    
    stages {
        
        stage("Build") {
            
            steps {
                when {
                    expression {
                    BRANCH_NAME == 'master'
                    }
                }
            echo 'Building the application.....'
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
