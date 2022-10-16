pipeline {
    agent {
        label 'JDK-11'
    }
    triggers { 
        pollSCM('* * * * *') 
        }
    stages {
        stage('clone') {
            steps {
                git url: "https://github.com/GUDAPATIVENKATESH/shopizer.git" ,
                    branch: "devlop"
            }
        }
        stage('build') {
            steps {
                sh "mvnw clean install"
            }
        }
    }
}