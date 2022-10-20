pipeline {
    parameters {
        choice(name: 'BRANCH', choices: ['master', 'main', 'none'], description: 'Pick something')
        string(name: 'GOAL1', defaultValue: 'mvn clean', description: 'enter maven goal')
        string(name: 'GOAL2', defaultValue: 'mvn clean', description: 'enter maven goal')
    }
    stages {
        agent {
            label('NODE1')
        }
        stage('clone_to_node1') {
            steps {
                git url : 'https://github.com/GUDAPATIVENKATESH/shopizer.git' ,
                branch : '${params.BRANCH}'
            }
        }
        stage('build_in_node1') {
            steps {
                sh '${params.GOAL1}'
            }
        }
    }
    stages {
        agent {
            label('NODE2')
        }
        stage('clone_node2') {
            steps {
                git url : 'https://github.com/GUDAPATIVENKATESH/shopizer.git' ,
                branch : '${params.BRANCH}'
            }
        }
        stage('build_in_node2') {
            steps {
                sh '${params.GOAL2}'
            }
        }
    }
}