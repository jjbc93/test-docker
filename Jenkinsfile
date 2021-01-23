pipeline {
    agent {
        docker {
            image 'node'
            args '-p 3000:3000'
        }
    }                       
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('test') {
            steps {
                sh 'npm run test'
            }
        }

        stage('Deploy') {
            steps {
                sh '(npm run start&)'
            }
        }
    }
}