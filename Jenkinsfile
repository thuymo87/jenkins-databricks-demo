pipeline {
    agent any

    stages {
        stage('Deploy to Databricks') {
            steps {
                sh '''
                    echo "Deploying notebook to Databricks..."
                    databricks configure --token "${env.DATABRICKS_TOKEN}"
                    databricks workspace import --json --language PYTHON \
                        hello_world.ipynb \
                        /Shared/hello_world_notebook
                    echo "Notebook deployment complete."
                '''
            }
        }
    }
}
