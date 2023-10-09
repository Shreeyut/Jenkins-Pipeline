pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo 'Building the code using Maven'
            }
        }
        stage('Unit and Integration Tests'){
            steps{
                echo 'Unit tests in progress using Mocha'
                echo 'Integration tests in progress using Tessy'
            }
            post{
                success{
                    emailext(
                        subject: 'Unit and Integration Tests status',
                        to: 'shreeyutshrestha@gmail.com',
                        body: 'Unit and Integration Tests successfuly completed.',
                        attachLog: true
                    )
                }
                failure{
                    emailext(
                        subject: 'Unit and Integration Tests status',
                        to: 'shreeyutshrestha@gmail.com',
                        body: 'Unit and Integration Tests Failed. Check logs.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo 'Analyzing code using SonarQube'
            }
        }
        stage('Security Scans'){
            steps{
                echo 'Performing Secuirty Scan using Acunetix'
            }
            post{
                success{
                    emailext(
                        subject: 'Security Scan status',
                        to: 'shreeyutshrestha@gmail.com',
                        body: 'Security Scan successfuly completed.',
                        attachLog: true
                    )
                }
                failure{
                    emailext(
                        subject: 'Security Scan status',
                        to: 'shreeyutshrestha@gmail.com',
                        body: 'Security Scan Failed. Check logs.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to staging'){
            steps{
                echo 'Deploying to staging server AWS EC2'
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo 'Performing Integration Tests on Staging'
            }
            post{
                success{
                    emailext(
                        subject: 'Integration Tests on Staging status',
                        to: 'shreeyutshrestha@gmail.com',
                        body: 'Integration Tests on Staging successfuly completed.',
                        attachLog: true
                    )
                }
                failure{
                    emailext(
                        subject: 'Integration Tests on Staging status',
                        to: 'shreeyutshrestha@gmail.com',
                        body: 'Integration Tests on Staging Failed. Check logs.',
                        attachLog: true
                    )
                }
            }
        }
        stage ('Deploy to Production'){
            steps{
                echo 'Deploying to production on AWS EC2 server'
            }
        }
    }
}
