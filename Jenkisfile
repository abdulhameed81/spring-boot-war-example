pipeline {
    agent any
    environment {
        name = 'AbdulSumi'
    }
    parameters{
        string(name: 'person', defaultValue: 'AbdulSumi', description: "who are you")
        booleanParam(name: 'IsMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Gangavathi','Koppal','Karnataka' ], description: "")
    }
    stages {
        stage('Run A command') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
                
            }
        }
         stage('Environment Variables') {
             environment {
                 username = 'AbdulRukhi'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Deploy on test') {
            steps {
                echo 'deploy on test'
                sh 'echo "${name}"'
                sh 'echo "{person}"'
            }
        }
         stage('Countinue ?') {
            input {
                message "Should we Countinue?"
                ok "Yes we Should"
            }
            steps {
                echo 'deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        }
    }
    post{
        always {
            echo 'I will always say Hello again'
        }
        failure{
            echo 'failure'
        }
        success{
            echo 'success'
        }
    }
}
