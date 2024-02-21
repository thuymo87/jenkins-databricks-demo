pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/thuymo87/jenkins-databricks-demo.git'
            }
        }
        stage('Deploy to Databricks') {
            steps {
                sh '''
                    echo "Deploying Hello World script to Databricks..."
                    # Replace the following commands with actual Databricks CLI commands
                    # For simplicity, we're just echoing the deployment steps
                    echo "Databricks deployment complete."
                '''
            }
        }
    }
}
