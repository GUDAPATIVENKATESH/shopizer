pipeline {
    agent none
    parameters {
        choice(name: 'BRANCH1', choices: ['master', 'devlop', 'relese'], description: 'Pick something')
        string(name: 'GOAL1', defaultValue: 'mvn clean', description: 'enter maven target goal1')
        choice(name: 'BRANCH2', choices: ['master', 'devlop', 'relese'], description: 'Pick something')
        string(name: 'GOAL2', defaultValue: 'mvn clean', description: 'enter maven target goal2')
    }   
    stages {
        stage('clone_node1') {
            agent { label 'JDK' }
            steps {
                git url : 'https://github.com/GUDAPATIVENKATESH/shopizer.git',
                branch : "${params.BRANCH1}"
            }
        }
        stage('build1') {
            agent { label 'JDK' }
            steps {
                sh "${params.GOAL1}"
            }
        }
        stage('clone_node2') {
            agent { label 'JVM' }
            steps {
                git url : 'https://github.com/GUDAPATIVENKATESH/shopizer.git',
                branch : "${params.BRANCH1}"
            }
        }
        stage('build2') {
            agent { label 'JVM' }
            steps {
                sh "${params.GOAL2}"
            }
        }
    }
}