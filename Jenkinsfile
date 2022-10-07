pipeline {
    agent {
        label 'JDK11'
    }
    triggers { 
        pollSCM('* * * * *') 
        }
    stages {
        stage('clone') {
            steps {
                git url: "https://github.com/GUDAPATIVENKATESH/shopizer.git" ,
                    branch: "SPRINT_1_DEV"
            }
        }
        stage('build') {
            steps {
                sh "mvn clean"
                sh "mvn package"
                sh "mvn install"
            }
        }
    }
}