pipeline {
    agent any
    

    stages {
        stage('Cron-activated stage') {
            when {
                expression { env.five }
            }
            steps {
                echo 'This stage only runs when triggered by cron.'
                // Add your build steps here
            }
        }

        stage('Manual stage 1') {
            when {
                not {
                 expression { env.five  }
                
            }
            steps {
                echo 'This stage can only be run manually.'
                // Add your build steps here
            }
        }

        stage('Manual stage 2') {
            when {
                not {
                    expression { env.five }
                }
            }
            steps {
                echo 'This stage can also only be run manually.'
                // Add your build steps here
            }
        }
    }

    triggers {
        //test
        parameterizedCron('''
        */5 * * * * %five=true
        ''')
    }
}
