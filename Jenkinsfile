pipeline {
    agent any
    triggers {
        pollSCM('H/2 * * * *')
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
                echo "${env.BUILD_ID}"
            }
        }
    }
    post { 
        always { 
            echo "Build: ${currentBuild.number} Say Hello to my lil friend, MAFAKA!"
        }
    }
}
