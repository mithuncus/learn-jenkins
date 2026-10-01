
pipeline {
//     agent {
//     node {
//         label 'AGENT-1'
    
//     }
//    }
 agent any
   environment {
    Greetings= 'hello jenkins'
   }
   options {
    timeout (time: 1, unit: 'HOURS' )
    disableConcurrentBuilds(). //this line will disable the concurrent builds 

    )
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                sh """
                echo "here i wrote shell script "
                echo " $Greetings "
                env 
                """
            }
        }
        stage('check parameters') {
            steps {
                sh """
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                """
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