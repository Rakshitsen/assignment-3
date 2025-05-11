pipeline {
    agent none
    environment {
        CURRENT_BRANCH = "${env.BRANCH_NAME}"
        GIT_URL = 'https://github.com/Rakshitsen/assignment-3.git'
    }
    stages {
        stage('push-to-prod') {
            agent { label 'agent002' }
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                echo 'This is cloning the repo for production'
                git branch: 'master', credentialsId: 'Github_cred', url: env.GIT_URL
                echo 'Code cloned successfully to production'
            }
        }

        stage('push-to-test') {
            agent { label 'agent001' }
            when {
                expression { env.BRANCH_NAME == 'test' }
            }
            steps {
                echo 'This is cloning the repo for testing'
                git branch: 'master', credentialsId: 'Github_cred', url: env.GIT_URL
                echo 'Code cloned successfully to testing'
            }
        }
    }
}
