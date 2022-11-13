pipeline {
    agent any

    stages {
        stage('AWS STS') {
            steps {
                echo 'AWS STS'
                sh 'aws sts get-caller-identity'
            }
        }
        stage('AWS S3 listar') {
            steps {
                sh 'aws s3 ls'
            }
        }
        stage('Git Clone') {
            steps {
                sh 'rm -rf Desafio3/'
                sh 'git clone https://github.com/lucaspedernera27/Desafio3.git'
                sh 'ls -lrt Desafio3/'
            }
        }
         stage('Upload to S3') {
            steps {
                sh 'aws s3 cp Desafio3 s3://desafio3-csv-loader-bucket --recursive'
            }
        }
    }
}
