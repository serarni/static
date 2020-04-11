pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!!"'
            }
        }
        stage('Upload to AWS') {
            steps {
                sh 'echo "Init_2..."'
                withAWS(region: 'us-east-2', credentials: 'aws-static') {
                    sh 'Uploading conteng to AWS bucket'
                    echo "Hola mundo jenkins" > index.html
                    s3Upload(file:'index1111.html', bucket:'111udacity-cap4-project')
                    sh 'index.html uploaded OK'
                }
            }
        }
    }
}
