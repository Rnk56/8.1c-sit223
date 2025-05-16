pipeline {
    agent any
   
      stages {

      //Stage 1: Build – Build the code using a build automation tool to compile and package
      //your code. You need to specify at least one build automation tool, e.g., Maven.
        
        stage("Build") {
            steps {
                sh "echo 'Using Maven to compile and package'"
            }
        }

    //Stage 2: Unit and Integration Tests – Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the 
    //application work together as expected. You need to specify test automation tools for this stage
        
        stage("Unit and Integration Tests") {
            steps {
                sh "echo 'Using JUnit to run unit tests' > test.log"
            }
            post {
                success {
                    mail to: 'ronik5819@gmail.com',
                        subject: 'Unit and Integration Tests stage Passed',
                        body: 'The Unit and Integration Tests stage completed successfully.'
                        attachmentsPattern: 'test.log'
                }
                failure {
                    mail to: 'ronik5819@gmail.com',
                        subject: 'Unit and Integration Tests stage Failed',
                        body: 'The Unit and Integration Tests stage failed, please re-check and fix.'
                        attachmentsPattern: 'test.log'
                }
            }
        }

    //Stage 3: Code Analysis – Integrate a code analysis tool to analyse the code and ensure
    //it meets industry standards. Research and select a tool to analyse your code using Jenkins
        
        stage("Code Analysis") {
            steps {
                sh "echo 'Using FindBugs to analyse the code and ensure'"
            }
        }

    //Stage 4: Security Scan – Perform a security scan on the code using a tool to identify any vulnerabilities. Research and select a tool to scan your code.

        stage("Security Scan") {
            steps {
                sh "echo 'Using DAST to identify any vulnerabilities' > security.log"
            }
            post {
                success {
                    mail to: 'ronik5819@gmail.com',
                        subject: 'Security Scan stage Passed',
                        body: 'Security stage stage completed successfully.'
                        attachmentsPattern: 'security.log'
                }
                failure {
                    mail to: 'ronik5819@gmail.com',
                        subject: 'Security Scan stage Failed',
                        body: 'Security Scan stage failed, please re-check and fix.'
                        attachmentsPattern: 'security.log'
                }
            }
        }
   
    //Stage 5: Deploy to Staging – Deploy the application to a staging server (e.g., AWS EC2 instance).
        
        stage("Deploy to Staging") {
            steps {
                sh "echo 'Using AWS EC2 to reploy the application to a staging server'"
            }
        }
        
  //Stage 6: Integration Tests on Staging – Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment.
        stage("Integration Tests on Staging") {
            steps {
                sh "echo 'Using Selenium, ato run integration tests on the staging environment'"
            }
        }

  //Stage 7: Deploy to Production – Deploy the application to a production server (e.g., AWS EC2 instance).
        
        stage("Deploy to Production") {
            steps {
                sh "echo 'Using AWS EC2 to reploy the application to a production server'"
            }
        }
    }
}
