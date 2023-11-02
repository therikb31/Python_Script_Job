pipeline {
    agent any

    parameters {
        string(name: 'ARGUMENTS', defaultValue: '', description: 'Arguments for the Python script')
    }

    environment {
        ENV_VAR_1 = 'value1'
        ENV_VAR_2 = 'value2'
    }

    stages {
        stage('Run Python Script') {
            steps {
                script {
                    sh "python3 my_script.py ${ENV_VAR_1} ${ENV_VAR_2} ${params.ARGUMENTS}"
                }
            }
        }
    }
}
