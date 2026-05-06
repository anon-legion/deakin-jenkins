pipeline {
    agent any

    environment {
        STAGING_SERVER  = 'ec2-user@<staging-ip>'
        PROD_SERVER     = 'ec2-user@<prod-ip>'
        SONAR_PROJECT   = 'myapp'
        APP_NAME        = 'myapp'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Stage 1: Build - Compiling and packaging the application using Maven.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests - Running tests'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis - Analysing code quality with SonarQube.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan - Scanning dependencies for CVEs using OWASP Dependency-Check.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging - Deploying application to AWS EC2 staging server.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging - Running integration tests against the staging environment.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production - Deploying validated application to AWS EC2 production server.'
            }
        }


    }

    post {
        success { echo 'Pipeline completed successfully.' }
        failure { echo 'Pipeline failed. Check stage logs above.' }
    }
}
