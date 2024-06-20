pipeline {
    agent {
        label "Slave01"
    }
    triggers {
        pollSCM('H/2 * * * *')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Parallel Hello') {
            failFast true
            parallel {
                stage('Parallel Hello1') {
                    steps {
                        echo 'Hello World Slave02 ${params.action}'
                    }
                }
                stage('Parallel Hello2') {
                    steps {
                        echo 'Hello World Slave03'
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
