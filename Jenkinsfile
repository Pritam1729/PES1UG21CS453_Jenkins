pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS641-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying..."'
                sh './non_existent_deploy_script.sh'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
