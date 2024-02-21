pipeline {
    agent any

    environment {
        // Define environment variables
        DATABRICKS_TOKEN = credentials('dapi0b777dec2e29b58533d7e115e5c4b022')
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
