pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Execute Shell Script') {
            steps {
                script {
                    // Print current directory to confirm workspace
                    echo "Current directory is:"
                    sh 'pwd'

                    // List files in the current directory
                    echo "Listing files in the current directory:"
                    sh 'ls -la'

                    // Execute the shell script
                    echo "Executing list_files.sh script:"
                    def result = sh(script: './list_files.sh', returnStdout: true).trim()

                    // Print the output to the Jenkins console
                    echo "The result of the script is: \n${result}"
                }
            }
        }
    }
}

