pipeline {
    agent {
        label 'JDK-11'
    }
    triggers { 
        cron('30 17 * * 1-5') 
        }
    stages {
        stage('clone') {
            steps {
                git url: "https://github.com/GUDAPATIVENKATESH/shopizer.git" ,
                    branch: "relese"
            }
        }
        stage('build') {
            steps {
                sh "mvn clean install"
            }
        }
    }
}