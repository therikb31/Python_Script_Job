pipeline {
    agent any
    environment {
        MY_NAME = "Rik Biswas"
    }
    parameters {
        string(description: 'Parameter', name:'PARAMETER_VARIABLE',defaultValue: 'Parameter')
    }

    stages {
        stage("build") {
            steps {
                script {
                    echo "Name: ${env.MY_NAME}"
                    echo "Params: ${params.PARAMETER_VARIABLE}"
                }
            }
        }

        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }

        stage("deploy") {
            steps {
                echo 'deploying the application'

            }
        }
    }
}