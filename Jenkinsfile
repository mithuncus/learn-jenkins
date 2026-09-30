
pipeline {
    agent {
    node {
        label 'AGENT-1'
    
    }
   }
// build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    // post build
     post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will say Hello again when build is success!'
        }
        failure { 
            echo 'I will say Hello again when build is failure!'
        }
        unstable { 
            echo 'I will say Hello again when build is unstable!'
        }
        aborted { 
            echo 'I will say Hello again when build is aborted!'
        }
        cleanup {
            echo 'Cleaning up...'
        }
    }
}