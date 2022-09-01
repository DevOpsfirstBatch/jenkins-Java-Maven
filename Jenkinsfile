properties([parameters([choice(choices: 'main \n feature-1\nfeature-2', name: 'build')])])

pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                echo "Pulling changes from branch ${params.build}"
                git changelog: false, credentialsId: 'GitID', poll: false, url: 'https://github.com/DevOpsfirstBatch/jenkins-maven-pipeline.git'
                
                }
            }
        }
       
    }
