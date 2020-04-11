pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                sh 'echo "Init.."'
                withAWS(region:'us-east-2',credentials:'aws-static') {
                    sh 'echo "Uploading conteng to AWS bucket"'
                    s3Upload(file:'index.html', bucket:'udacity-cap4-project')
                    sh 'echo "index.html uploaded OK"'
                }
            }
        }
    }
}
