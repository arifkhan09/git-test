pipeline {
    agent any
    parameters {
        string(defaultValue: 'master', description: '', name: 'Branch')
    }
    stages {
        stage('Checkout') {
                       steps {
                               echo "Code Checkout from git..."
                               git branch: "${params.Branch}", url: "https://github.com/dgadiraju/ccdemo.git"
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
        
        stage('Build') {
                       steps {
                               echo "Packaging..."
                               sh "sbt package"
            }
        }
        
        stage('Publish') {
            steps {
                echo 'Publishing..'
                script{
                     def server = Artifactory.server 'jenkins-artifactory-server'
                     def uploadSpec = """{
                                "files": [
                                { 
                                     "pattern": "**/target/scala-2.11/*.jar",
                                     "target": "sbt-dev-local/ccdemo_2.11-1.0.jar"
                                  }
                                ]
                             }"""
                             server.upload(uploadSpec)
                }
            }
         }
    }    
}
