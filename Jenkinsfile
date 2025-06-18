pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('pre-deploy') {
            steps {
               sh 'echo pre-Deploying....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post { 
        always { 
            echo 'This section always runs!'
        }
        sucess {
             echo 'This section runs when pipeline sucess'
        }
        failure {
             echo 'This section runs when pipeline failed'
        }
    }
}