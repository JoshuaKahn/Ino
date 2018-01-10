 pipeline { 
    agent none
    stages {
        stage('Build') {
            agent {
                label 'master'
            }
            steps {
                sh 'python3 hello.py'
            }
        }
        stage('test') {
            agent {
                label 'test_slave'
            }
            steps {
              sh 'py.test --junitxml results.xml hello.py'
              sh 'make check || true'
            }
            post {
                always {
                    junit 'results.xml'
                }
            }
        }
    }
}