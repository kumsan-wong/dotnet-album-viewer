pipeline {
    agent none
    triggers {
        pollSCM('H/2 * * * *')
    }
    stages {
        stage('Hello') {
            steps {
                echo "Hello World ${env.NODE_NAME}"
            }
        }
        stage('Parallel Hello') {
            failFast true
            parallel {
                stage('Parallel Hello1') {
                    agent any
                    steps {
                        echo "Hello World ${env.NODE_NAME} ${params.action}"
                    }
                }
                stage('Parallel Hello2') {
                    agent any
                    steps {
                        echo "Hello World ${env.NODE_NAME}"
                    }
                }
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
