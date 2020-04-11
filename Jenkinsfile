pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Init..."'
                withAWS(credentials: 'aws-static', region: 'eu-central-1') {
                    sh 'Uploading conteng to AWS bucket'
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'file.txt', bucket:'jenkins-serarni-udacity-p4')
                    sh 'index.html uploaded OK'
                }
            }
        }
    }
}
