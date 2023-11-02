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
                    def scriptPath = 'my_script.py'
                    
                    try {
                        if(!fileExists(scriptPath)) {
                            error ("Script ${scriptPath} not found.")
                        }

                        def result = sh(script: "python3 my_script.py ${ENV_VAR_1} ${ENV_VAR_2} ${params.ARGUMENTS}", returnStatus: true)

                        if(result != 0) {
                            error("Script execution failed")
                        }
                    } catch(Exception e) {
                        error(${e.message})
                    }
                    // sh "python3 my_script.py ${ENV_VAR_1} ${ENV_VAR_2} ${params.ARGUMENTS}"
                }
            }
        }
    }
}

def fileExists(filePath) {
    def file = new File(filePath)
    return file.exists()
}