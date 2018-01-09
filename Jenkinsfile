 pipeline { 
    agent { docker 'python:3.5.1' }
    stages {
        stage('Build') {
            steps {
                sh 'python hello.py'
            }
        }
        stage('test') {
            steps {
              sh 'yum install pytest'
              sh 'py.test --junitxml results.xml hello.py'  
            }
        }
    }
}