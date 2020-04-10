pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello Wordl!"'
                sh '''
                  echo "Multiple shell steps work too"
                  ls -lah
                '''
            }
        }
    }
}
