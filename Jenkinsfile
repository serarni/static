pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Init_2..."'
                withAWS(region:'us-east-2',credentials:'aws-static') {
                    sh 'echo "Uploading conteng to AWS bucket"'
                    /*echo "Hola mundo jenkins" > index.html*/
                    s3Upload(file:'index.html', bucket:'udacity-cap4-project')
                    sh 'echo "index.html uploaded OK"'
                }
            }
        }
    }
}
