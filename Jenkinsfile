pipeline {
    agent {
        label "AGENT-1"
    }

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
               //error 'predeploy failing' //the post action should show failure only
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    //this is overall pipeline condition
    post { 
        always { 
            echo 'This section always runs!'
        }
        success {
            echo 'This section runs when pipeline sucess'
        }
        failure {
            echo 'This section runs when pipeline failed'
        }
    }
}