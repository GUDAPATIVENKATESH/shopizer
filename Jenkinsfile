pipeline {
    agent none
    stages {
        stage('in_node1') {
            agent { label 'NODE1' }
            steps {
                git url : 'https://github.com/GUDAPATIVENKATESH/shopizer.git' ,
                branch: 'master'
            }
        }
        stage('in') {
            agent { label 'NODE1' }
            steps {
                sh 'mcn clean'
            }
        }
        stage('in_node2') {
            agent { label 'NODE2' }
            steps {
                git url : 'https://github.com/GUDAPATIVENKATESH/shopizer.git' ,
                branch : 'devlop'
            }
        }
        stage('in2') {
            agent { label 'NODE2' }
            steps {
                sh 'mvn package'
            }
        }
    }
}