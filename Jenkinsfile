pipeline {
    agent any
    stages {
        stage('Checkout') {
                       steps {
                               echo "Code Checkout fro git..."
                               git "https://github.com/arifkhan09/sparkapplication.git"
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
