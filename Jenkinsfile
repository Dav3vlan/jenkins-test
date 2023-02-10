pipeline {
    agent any
    

    stages {
        stage('Debug 01') {
            steps {
                echo sh(script: 'env|sort', returnStdout: true)
                // Add your build steps here
            }
        }
        stage('Cron-activated stage') {
            when {
                expression { env.FIVER == env.FIVER.toUpperCase() }
            }
            steps {
                echo 'This stage only runs when triggered by cron.'
                // Add your build steps here
            }
        }

        stage('Manual stage 1') {
            when {
                not {
                    expression { env.FIVER == env.FIVER.toUpperCase() }
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
                    expression { env.FIVER == env.FIVER.toUpperCase() }
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
        // parameterizedCron("*/5 * * * * % FIVER=true")
        // test 
       
    }
}
