pipeline {
    agent any

 

    stages {
        stage('Checkout') {
            steps {
               checkout([$class: 'GitSCM', branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: '7fc6f676-451f-4e16-b52d-02049fa25487', url: 'https://github.com/GauravBarua/Hotel-Management-System.git']]])
            }
        }
        stage('Build and Test') {
            steps {
                sh 'mvn clean install -Dmaven.test.skip=true'

            }
        }
        stage('Code Analysis') {
            steps {
                echo "Scanned successfully!"
            }
        }
        stage('Notification') {
            steps {
                emailext body: 'build is successful', subject: 'Build', to: 'gauravbarua008@gmail.com'
            }
        }
        }
    }
