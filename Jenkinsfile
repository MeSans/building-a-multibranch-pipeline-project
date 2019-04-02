pipeline {
     agent any
    //  {
    //     docker  
    //     {
    //         image 'node:6-alpine'
    //         args '-p 3000:3000 -p 5000:5000' 
    //     }
    // }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deploy for development') {
            when {
                branch 'dev'
            }
            steps {
                echo 'Delivering the site to development env'
            }
        }
        stage('Deploy for prod') {
            when {
                branch 'prod'
            }
            steps {
                echo 'Delivering the site to production env.'
            }
        }
    }
}