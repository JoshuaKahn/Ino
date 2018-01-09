 pipeline { 
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 hello.py'
            }
        }
        stage('test') {
            steps {
              sh 'py.test --junitxml results.xml hello.py'
              sh 'make check || true'
              junit '**/target/*.xml'
            }
        }
    }
}