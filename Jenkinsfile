pipeline {
    agent any
    
    tools {
        // To specify maven to use
        maven "mvn-3.9.8"
    }
    stages {
        stage ('Checkout') {
            steps {
                // Checkout the source repo from scm
                git branch: 'main', url: 'https://github.com/Nithisha-BR/remotejun24.git'
            }
        }
        stage ('Build') {
            steps {
                //Use echo
                sh 'mvn clean package'
            }
        }
        stage ('Test') {
            steps {
                //Run a tests if applicabel
                sh 'mvn test'
            }
        }
    }
    post{
        success{
            //This will be executed if the pipeline execution is successful
            echo 'Pipeline executed successfully!'
        }
        failure{
            //This will be executed if the pipeline execution fails
            echo 'Pipeline failed!'
        }
    }
}
