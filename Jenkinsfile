pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh '''
                    echo "Checking out SCM."
                   '''
            }
        }
        stage("Test") {
            steps {
                sh '''
                    echo "Running test script"
                   '''
            }
        }
        stage("Email Notification") {
            steps {
                mail(
                    body: "Build and Test completed.", 
                    subject: 'Pytest completed.', 
                    to: 'ibrahima.diallo1289@gmail.com')
                    }
                }
            }
            post {
                always {
                    junit 'test_result/test_result_${BUILD_NUMBER}.xml'
                }
                success {                   
                    echo "Flask App Up and running!!"
                }
                failure {
                    echo 'Build stage failed'
                    error('Stopping early…')
                }
        
    }
}
