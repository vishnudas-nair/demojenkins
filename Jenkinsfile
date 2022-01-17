pipeline {
    agent any
    environment{
        name = 'gaurav'
    }
    parameters {
        string(name : 'person', defaultValue: 'Vishnu', description: 'Who are you')
        booleanParam(name : 'isMale', defaultValue: true, description: 'Who are you')
        choice(name : 'City', choices: ['Jaipur', 'Mumbai' , 'Pune'], description: '')
        
    }

    stages {
        stage('Run a Command') {
            steps {
               sh '''
               ls
               pwd
               date
               cal 2021
               '''
                
            }
        }
        
        stage('Environment Variable') {
            environment{
               name = 'vishnu'
            }
            steps {
                sh 'echo "$BUILD_ID" '
                sh 'echo "$name" '
            }
        }
        
        stage('Parameters') {
            steps {
                sh 'echo "$person" '
            }
        }
        
        stage('Continue ?') {
            input {
                message "Should we continue ?"
                ok "Yes we should"
            }
            steps {
                echo 'Deploy on Prod'
            }
        }
        
        stage('Deploy on Prod') {
            steps {
                eco 'Deploy on Prod'
            }
        }
    }
    post {
        always {
            echo "I will always say hello again"
        }
        failure {
            echo "Failed"
        }
        success {
            echo "Build is working fine."
        }
    }
}
