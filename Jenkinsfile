pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example: Use Maven to build the code
                sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Example: Run unit tests using JUnit
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Example: Use SonarQube for code analysis
                sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
                // Example: Use OWASP Dependency-Check for security scanning
                sh 'dependency-check'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Example: Deploy to staging (e.g., using AWS CLI)
                sh 'aws deploy push ...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Example: Run integration tests on staging (e.g., Postman or Selenium)
                sh 'postman run tests'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Example: Deploy to production (e.g., AWS CLI)
                sh 'aws deploy push ...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
        success {
            mail to: 'dewumisamuduni@gmail.com',
                 subject: "Pipeline Success",
                 body: "The pipeline
