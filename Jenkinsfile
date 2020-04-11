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
                withAWS(credentials: 'aws-static', region: 'eu-central-1') {
                    sh 'Uploading conteng to AWS bucket'
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-serarni-udacity-p4')
                    sh 'index.html uploaded OK'
                }
            }
        }
    }
}
