pipeline {
    agent any
    stages {
        stage('Checkout') {
                       steps {
                               echo "Code Checkout from git..."
                               git "https://github.com/arifkhan09/sparkapplication.git"
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
