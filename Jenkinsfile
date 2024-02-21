pipeline {
    agent any

    environment {
        // Define environment variables
        DATABRICKS_TOKEN = credentials('databricks-token')
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/thuymo87/jenkins-databricks-demo.git'
            }
        }
        stage('Deploy to Databricks') {
            steps {
                sh '''
                    echo "Deploying notebook to Databricks..."
                    databricks workspace import --json --language PYTHON \
                        hello_world.ipynb \
                        /Shared/hello_world_notebook
                    echo "Notebook deployment complete."
                '''
            }
        }
    }
}
