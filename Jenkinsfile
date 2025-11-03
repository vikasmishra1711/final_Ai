pipeline {
    agent any

    environment {
        // GitHub credentials ID in Jenkins
        GIT_CREDENTIALS_ID = 'github-creds'
    }

    stages {
        stage('Checkout SCM') {
            steps {
                git(
                    url: 'https://github.com/Divyanshu592/ai_final.git',
                    branch: 'master',
                    credentialsId: "${GIT_CREDENTIALS_ID}"
                )
            }
        }
    }

    post {
        always {
            echo "Cleaning workspace..."
            cleanWs()
        }
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed. Check logs."
        }
    }
}
