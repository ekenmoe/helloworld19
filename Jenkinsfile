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
                echo 'deploying CD application......'
                sshPublisher(publishers: [sshPublisherDesc(configName: 'docker-host', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''docker rmi holliday:2.0 -f; 
docker build -t holliday:2.0 .; 
docker tag holliday:2.0 ekenmoe/holliday:2.0 ;
docker push ekenmoe/holliday:2.0
''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: 'webapp/target', sourceFiles: '**/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            
            }
        
       }
  
        
    }
    
}
