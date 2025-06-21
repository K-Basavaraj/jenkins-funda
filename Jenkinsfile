pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 5, unit: 'MINUTES') //timeout
        disableConcurrentBuilds()  //disable concurent build one after one
    //retry(1)           //retry faild stage
    }
    parameters {   //buildwith parameters
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'sleep 10'
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
        stage('print parameters') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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
