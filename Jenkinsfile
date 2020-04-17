pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code Checkout fro git..."
                git "https://github.com/arifkhan09/sparkapplication.git"
            }
        }
        
        stage('Compile') {
            steps {
                echo "Compiling..."
                sh "{tool name: 'sbt' type: 'org.jvnet.hudson.plugins.SbtPluginBuilder_SbtInstallation'}/sbt-luncher_0.13.8/bin/sbt compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "{tool name: 'sbt' type: 'org.jvnet.hudson.plugins.SbtPluginBuilder_SbtInstallation'}/sbt-luncher_0.13.8/bin/sbt test"
            }
        }

        stage('Package') {
            steps {
                echo "Packaging..."
                sh "{tool name: 'sbt' type: 'org.jvnet.hudson.plugins.SbtPluginBuilder_SbtInstallation'}/sbt-luncher_0.13.8/bin/sbt package"
            }
        }

    }
}
