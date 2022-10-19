pipeline {
    agent { label 'ubuntu_node-1' }
    triggers {
        cron('*/5 * * * *')
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
             
        stage('archive facts')
            steps{
               includes : '**/target/*.jar' 
            }
    stage('reporting') {
            steps {
                junit testResults: 'target/surefire-reports/*.xml'
            }
        }
      }
}