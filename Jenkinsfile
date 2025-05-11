pipeline {
    environment {
        CURRENT_BRANCH = "${env.BRANCH_NAME}"
    }
        stage('push-to-prod') {
            agent { label 'agent002' }
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
           steps{
                echo 'this is cloning the repo'
                git branch: 'master', credentialsId: 'Github_cred', url: 'https://github.com/Rakshitsen/jenkins-case-study.git'
                echo 'Code clone successfully'
            }
        }
         stage('push-to-test') {
            agent { label 'agent001' }
            when {
                expression { env.BRANCH_NAME == 'test' }
            }
           steps{
                echo 'this is cloning the repo'
                git branch: 'master', credentialsId: 'Github_cred', url: 'https://github.com/Rakshitsen/jenkins-case-study.git'
                echo 'Code clone successfully'
            }
        }

}
