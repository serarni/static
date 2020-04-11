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
                sh 'echo "Testing sh commands..."'
                withAWS(credentials: 'aws-static', region: 'us-east-2') {
                    sh 'Uploading conteng to AWS bucket'
                    sh 'aws s3 cp index.html s3://udacity-cap4-project/'
                }
            }
        }
        /*stage('Upload to AWS') {
            steps {
                sh 'echo "Init_2..."'
                withAWS(credentials: 'aws-static', region: 'eu-central-1') {
                    sh 'Uploading conteng to AWS bucket'
                    echo "Hola mundo jenkins" > index.html
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-serarni-udacity-p4')
                    sh 'index.html uploaded OK'
                }
            }
        }*/
    }
}
