pipeline {
    agent any
    triggers {
        cron('* */30 * * *')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hello2') {
            steps {
                echo 'Hello World2'
            }
        }
    }
}
