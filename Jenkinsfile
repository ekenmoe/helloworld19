pipeline {
    
    agent any 
    
    stages {
        
        stage("Build") {
            
            steps {
                when {
                    expression {
                    BRANCH_NAME == 'master' && CODE_CHANGE == true
                    }
                }
            echo 'Building the application.....'
            }
        }
        
        stage("Test") {
            
            steps {
                when {
                    expression {
                    BRANCH_NAME == 'master' || BRANCH_NAME == 'request'
                    }
                }
            echo 'Testing the application......'
            }
        }
   stage("Deploy") {
            
            steps {
            echo 'Deploy the application......'
            }
        }
  
    }
    post {
        always {
        echo 'sent email to all team member ....'
        }
        failure {
        echo 'sent report email to both ops and dev team....'
        }
        
    }
}
