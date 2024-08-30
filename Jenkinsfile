pipeline {
    agent any

    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                // using maven: to build and package the Java application
                echo 'Building the code...'
                echo 'Using Maven to build by compiling and packaging the code...'
            }
        }

        // Stage 2: Unit and Integration Tests
        stage('Unit and Integration Tests') {
            steps {
                // using JUnit: run unit tests for code functionality
                // using TestNG: integration tests to ensure each component works together seamlessly
                echo 'Running unit tests with JUnit...'
                echo 'Using TestNG for integration testing...'
            }
            post {
                always {
                    emailext(
                        to: "ctrlvish@gmail.com",
                        subject: "Unit and Integrations results: ${currentBuild.currentResult}",
                        body: "The build ${currentBuild.fullDisplayName} has completed \n Status: ${currentBuild.currentResult} \n See attached logs for more details.",
                        attachLog: true
                    )
                }
            }
        }

        // Stage 3: Code Analysis
        stage('Code Analysis') {
            steps {
                // using Checkstyle: code analysis to meet industry standards
                echo 'Analyzing the code using Checkstyle...'
            }
        }

        // Stage 4: Security Scan
        stage('Security Scan') {
            steps {
                // using ZAP: security testing and to identify vulnerabilities
                echo 'Using ZAP for security scanning...'
            }
            post {
                always {
                    emailext(
                        to: "ctrlvish@gmail.com",
                        subject: "Security Scan results: ${currentBuild.currentResult}",
                        body: "The build ${currentBuild.fullDisplayName} has completed \n Status: ${currentBuild.currentResult} \n See attached logs for more details.",
                        attachLog: true
                    )
                }
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                // AWS CLI: deploy to an EC2 instance (staging)
                echo 'Using AWS CLI to deploy the application to staging...'
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                // using TestNG: integration tests on staging
                echo 'Using TestNG for integration testing on staging.'
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                // using AWS CLI: to deploy to production
                echo 'Deploying to the production server using AWS CLI...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}