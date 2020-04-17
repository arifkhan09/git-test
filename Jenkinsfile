pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code Checkout fro git..."
                git 
            }
        }
	    
	stage('Compile') {
            steps {
                echo "Compiling..."
                sh "/usr/local/bin/sbt compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "/usr/local/bin/sbt test"
            }
        }

        stage('Package') {
            steps {
                echo "Packaging..."
                sh "/usr/local/bin/sbt package"
            }
        }

    }
}
