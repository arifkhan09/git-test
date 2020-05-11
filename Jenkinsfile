pipeline {
    agent any
    parameters {
        sring(defaultValue: 'master', description: '', name: 'Branch')
    }
    stages {
        stage('Checkout') {
                       steps {
                               echo "Code Checkout from git..."
                               git branch: ${params.Branch}, url: "https://github.com/dgadiraju/ccdemo.git"
                        }
        }
        
        stage('Compile') {
            steps {
                echo "Compiling..."
                sh "sbt compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "sbt test"
            }
        }
        
        stage('Package') {
                       steps {
                               echo "Packaging..."
                               sh "sbt package"
            }
        }

    }
}
