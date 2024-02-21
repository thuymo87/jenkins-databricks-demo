pipeline {
    agent any

    stages {
        stage('Deploy to Databricks') {
            steps {
                sh '''
                    echo "Deploying notebook to Databricks..."
                    databricks configure --token "dapi0b777dec2e29b58533d7e115e5c4b022"
                    databricks workspace import --json --language PYTHON \
                        hello_world.ipynb \
                        /Shared/hello_world_notebook
                    echo "Notebook deployment complete."
                '''
            }
        }
    }
}
