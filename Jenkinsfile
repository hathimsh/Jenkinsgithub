pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                sh 'mvn test'
                // Run integration tests here
            }
        }

        stage('Code Analysis') {
            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Security Scan') {
            steps {
                sh 'mvn dependency-check:check -Dformat=ALL -DfailBuildOnCVSS=9'
            }
        }

        stage('Deploy to Staging') {
            steps {
                // Use Jenkins deployment plugin or AWS CLI to deploy to staging
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment
            }
        }

        stage('Deploy to Production') {
            steps {
                // Use Jenkins deployment plugin or AWS CLI to deploy to production
            }
        }
    }

    post {
        success {
            emailext body: 'The build succeeded!',
                     subject: 'Build Success',
                     to: 'hshahulhameed@deakin.edu.au'
        }
        failure {
            emailext body: 'The build failed. Please check the logs for details.',
                     subject: 'Build Failure',
                     to: 'hshahulhameed@deakin.edu.au'
        }
    }
}
