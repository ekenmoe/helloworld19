pipeline {
    agent any
    triggers {
        cron( 'H/1 * * * *' )
    }
    tools {
        maven 'M2_HOME'
      
    }
    stages {
      stage('Build'){
        steps {
          echo "Build step"
          sh 'mvn clean'
          sh 'mvn install'
          sh 'mvn package'
        }
      
      
      }
        stage('test '){
        steps {
            retry(4){
          echo  "test step"
            }
          sh 'mvn test'
        }
      
      
      }
    }
}
