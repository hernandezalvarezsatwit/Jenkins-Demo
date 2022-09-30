pipeline {
    agent any

    stages {
        stage('Build1') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/car.txt'
                sh 'echo "chassis" >> build/car.txt'
                sh 'echo "engine" >> build/car.txt'
                sh 'echo "body" >> build/car.txt'
            }
        }
        stage('Test1') {
            steps(){
                sh 'test -f build/car.txt'
                sh 'grep "chassis" build/car.txt'
                sh 'grep "engine" build/car.txt'
                sh 'grep "body" build/car.txt'
            }
        }
        stage('Publish1'){
            steps{
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
