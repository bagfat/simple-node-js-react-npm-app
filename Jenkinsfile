pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'  // Menjalankan app
                input message: 'Finished using the web site? (Click "Proceed" to continue)'  // Tunggu user klik
                sh './jenkins/scripts/kill.sh'  // Matikan app
            }
        }
    }
}
