#!groovy
@Library('my-shared-library') _

pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                echo 'Hello first'
            }
        }
        stage ('Testing Stage') {
            
            steps {
                echo 'Hello Second'
            }
        }
        stage ('Deployment Stage') {
            steps {
                echo 'Hello Third'
            }
            post {
                success {
                    myNewLib (channel: '#work-test', message: "Build is success (${env.BUILD_URL})")
                }
                failure {
                    myNewLib (channel: '#libra-test', message: "Build failed (${env.BUILD_URL})")
                }
            }
        }
    }
}
