pipeline {
    agent any
    

    stages {
        stage('Cron-activated stage') {
            when {
                expression { env.BRANCH_NAME == env.BRANCH_NAME.toUpperCase() }
            }
            steps {
                echo 'This stage only runs when triggered by cron.'
                // Add your build steps here
            }
        }

        stage('Manual stage 1') {
            when {
                not {
                    expression { env.BRANCH_NAME == env.BRANCH_NAME.toUpperCase() }
                }
            }
            steps {
                echo 'This stage can only be run manually.'
                // Add your build steps here
            }
        }

        stage('Manual stage 2') {
            when {
                not {
                    expression { env.BRANCH_NAME == env.BRANCH_NAME.toUpperCase() }
                }
            }
            steps {
                echo 'This stage can also only be run manually.'
                // Add your build steps here
            }
        }
    }

    triggers {
        cron('*/5 * * * *')
    }
}
