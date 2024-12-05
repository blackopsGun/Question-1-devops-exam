pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/blackopsGun/Question-1-devops-exam.git'
        BRANCH_NAME = 'main' 
        SCRIPT_NAME = 'Question-1-devops-exam/system-date_time.sh'  
    }

    stages {
        stage('Checkout Code') {
            steps {
                git url: "${REPO_URL}", branch: "${BRANCH_NAME}"
            }
        }

        stage('Run Shell Script') {
            steps {
                sh 'chmod +x ${SCRIPT_NAME}'

                sh './${SCRIPT_NAME}'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}

