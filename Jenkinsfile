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
                    newnotifier (channel: '#work-test', color: '#00FF00', email: 'vijay45kmar@gmail.com', message: "Build is success (${env.BUILD_URL})")
                }
                failure {
                    newnotifier (channel: '#libra-test', color: '#FF0000', email: 'vijay45kmar@gmail.com', message: "Build failed (${env.BUILD_URL})")
                }
            }
        }
    }
}
