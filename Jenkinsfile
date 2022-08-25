pipeline {
    agent any

    tools {
        maven "maven3.8.6"
        jdk "java1.8"
    }

    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
        stage('Checkout') {
            steps {
                git changelog: false, credentialsId: 'GitID', poll: false, url: 'https://github.com/DevOpsfirstBatch/jenkins-maven-pipeline'
                }
            
            }
        }
        
        
        stage('Build') {
            steps {
                {
                sh 'mvn -B -DskipTests clean package'
                }
            
            }
        }
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}
