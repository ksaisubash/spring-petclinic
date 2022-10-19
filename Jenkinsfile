pipeline {
    agent { label 'ubuntu_node-1' }
    triggers {
        cron('* * * * *')
    }
    stages {
        stage('Source Code') {
            steps {
                git url: 'https://github.com/ksaisubash/spring-petclinic.git', 
                branch: 'develop'
            }
            
        }
        stage(Maven) {
            steps {
                sh 'mvn package'
                  }
                      }
        
    }
}
