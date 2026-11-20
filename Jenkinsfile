pipeline {
    agent any

    stages {
        stage('Check Tools') {
            steps {
                sh 'git --version && docker --version && docker compose version'
            }
        }
        stage('Run Docker Test') {
            steps {
                sh 'docker run --rm hello-world'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
        always {
            sh 'docker ps -a'
        }
    }
}
