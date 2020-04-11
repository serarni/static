pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Init..."'
                withAWS(credentials: 'aws-static', region: 'eu-central-1') {
                    sh 'AWS loged'
                    s3Upload acl: 'Private', bucket: 'jenkins-serarni-udacity-p4', file: 'index.html'
                    sh 'index.html uploaded OK'
                }
            }
        }
    }
}
