pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build the code using a build automation tool to compile and package using Maven"
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo " Using JOne run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected."
                 post {
        success {
            emailext (
                    body: 'The build succeeded!',
                    subject: 'Build Success',
                     to: 'hshahulhameed@deakin.edu.au' ,
                     attachlog:true
                )
        }
            }
        }

        stage('Code Analysis') {
            steps {
                echo " Using Sonar Qube integrate a code analysis tool to analyse the code and ensure it meets industry standards."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Using OWASP perform a security scan on the code to identify any vulnerabilities"
                 post {
        success {
            emailext (
                    body: 'The build succeeded!',
                    subject: 'Build Success',
                     to: 'hshahulhameed@deakin.edu.au' ,
                     attachlog:true
                )
        }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo " Use Jenkins deployment plugin or AWS EC2 to deploy to staging"
               
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on staging environment"
                
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Use Jenkins deployment plugin or AWS CLI to deploy to production"
                
            }
        }
    }

   
}
    }
