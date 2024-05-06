pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build the code using a build automation tool to compile and package using Maven"
            }
        }
        stage('Art Added Stage') {
            steps {
                echo 'Art Added Stage.'
            }
            post {
                success {
                    emailext subject: 'Art Added Stage - now using your credentials Saloni',
                        body: 'Art Added Stage',
                        to: 'hathimshahul@gmail.com, hemmaphan@gmail.com',
                        attachLog: true
                }
            }
        }
    }
}
        

    
