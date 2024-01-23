pipeline {
    agent {
        node {
            label 'workstation'
        }
    }

    environment {
        SSH = credentials("SSH")
        DEMO_URL = 'google.com'
    }

    options {
        ansiColor('xterm')
    }

    triggers { pollSCM('H/2 * * * *') }

    parameters {
        string(name: 'APP_INPUT', defaultValue: '', description: 'Just Input')
    }

    stages {
        stage('Hello-1') {
            steps {
                echo 'Hello World'
                sh 'env'
                echo "APP_INPUT - ${params.APP_INPUT}"
            }
        }
    }

    post {
        always {
            sh 'echo Post'
        }
    }
}

//comment
