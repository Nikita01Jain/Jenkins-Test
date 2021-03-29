pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/test.txt'
                sh 'echo "intro" >> build/test.txt'
                sh 'echo "about" >> build/test.txt'
                sh 'echo "jenkins" >> build/test.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'test -f build/test.txt'
                sh 'grep "intro" build/test.txt'
                sh 'grep "about" build/test.txt'
                sh 'grep "jenkins" build/test.txt'
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
