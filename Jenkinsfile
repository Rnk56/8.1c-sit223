pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "echo 'Using Maven to compile and package'"
            }
        }

        stage("Unit and Integration Tests") {
            steps {
                sh "echo 'Using JUnit to run unit tests' > test.log"
            }
            post {
                success {
                    emailext(
                        to: "ronik5819@gmail.com",
                        subject: "Unit and Integration Tests stage Passed",
                        body: "The Unit and Integration Tests stage completed successfully.",
                        attachmentsPattern: 'test.log'
                    )
                }
                failure {
                    emailext(
                        to: "ronik5819@gmail.com",
                        subject: "Unit and Integration Tests stage Failed",
                        body: "The Unit and Integration Tests stage failed, please re-check and fix.",
                        attachmentsPattern: 'test.log'
                    )
                }
            }
        }

        stage("Code Analysis") {
            steps {
                sh "echo 'Using FindBugs to analyse the code and ensure'"
            }
        }

        stage("Security Scan") {
            steps {
                sh "echo 'Using DAST to identify any vulnerabilities' > security.log"
            }
            post {
                success {
                    emailext(
                        to: "ronik5819@gmail.com",
                        subject: "Security Scan stage Passed",
                        body: "Security Scan stage completed successfully.",
                        attachmentsPattern: 'security.log'
                    )
                }
                failure {
                    emailext(
                        to: "ronik5819@gmail.com",
                        subject: "Security Scan stage Failed",
                        body: "Security Scan stage failed, please re-check and fix.",
                        attachmentsPattern: 'security.log'
                    )
                }
            }
        }

        stage("Deploy to Staging") {
            steps {
                sh "echo 'Using AWS EC2 to deploy the application to a staging server'"
            }
        }

        stage("Integration Tests on Staging") {
            steps {
                sh "echo 'Using Selenium to run integration tests on the staging environment'"
            }
        }

        stage("Deploy to Production") {
            steps {
                sh "echo 'Using AWS EC2 to deploy the application to a production server'"
            }
        }
    }
}
