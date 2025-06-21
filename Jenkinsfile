pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 5, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                //sh 'sleep 10'
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
            deleteDir() //in jenkins this function will delete the workspace directory of the job on the agent (VM/container)
        }
        success {
            echo 'This section runs when pipeline sucess'
        }
        failure {
            echo 'This section runs when pipeline failed'
        }
    }
}
