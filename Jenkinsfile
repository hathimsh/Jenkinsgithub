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
                    to: 'hathimshahul@gmail.com',
                    subject: 'Build Success',
                    body: 'The build succeeded!',
                    attachLog: true
                )
        }
                      failure{
                         emailext (
                    to: 'hathimshahul@gmail.com',
                    subject: 'Build Failed',
                    body: 'The build not succeeded!',
                    attachLog: true
                )
                     }
            }
        }
        }

        
        }

       
   
}
    

    
