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
        stage('Parallel Hello') {
            parallel {
                stage('Parallel Hello1') {
                    agent {
                        label "Slave01"
                    }
                    steps {
                        echo 'Hello World Slave01'
                    }
                }
                stage('Parallel Hello2') {
                    agent {
                        label "Slave02"
                    }
                    steps {
                        echo 'Hello World Slave02'
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
