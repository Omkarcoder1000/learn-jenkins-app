pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'ls -la'
                sh 'touch container-no.txt'
            }
        }
        stage('Docker'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                echo 'hello docker'
                sh 'npm --version'
                sh 'ls -la'
                sh 'touch container-yes.txt'
            }
        }
    }
}
