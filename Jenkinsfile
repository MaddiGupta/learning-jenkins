//pipeline{
//    agent any
//
//    stages{
//
//      stage('TEST1'){
//        steps{
//          echo 'Test1'
//    }
//}
//
//        stage('TEST2'){
//             steps{
//                 echo 'Test2'
//                 emailext body: 'TEST', subject: 'TEST', to: 'Gupta@local.com'
//
//             }
//        }
//    }
//
//    post {
//        fixed {
//            echo "Hello"
//        }
//        failure {
//            echo "Failed State"
//            emailext body: 'TEST', subject: 'TEST', to: 'gupta@local.com'
//        }
//        cleanup {
//            echo "Common steps"
//        }
//    }
//
//}

//

//

//

//

// pipeline{
//     agent any
//
//         stages{
//             stage('one'){
//                 steps {
//                     echo 'ONE'
//                 }
//
//             }
//             stage('two'){
//                 when{
//                     expression {
//                         BRANCH_NAME == "master"
//                     }
//                 }
//                 steps{
//                     echo 'TWO'
//                 }
//             }
//         }
// }

//

pipeline {

    agent {
        node {
            label 'SLAVE01'
        }
    }

    tools {
        maven 'maven3'
    }

    options {
        buildDiscarder logRotator(
                    daysToKeepStr: '15',
                    numToKeepStr: '10'
            )
    }

    environment {
        APP_NAME = "DCUBE_APP",
        APP_ENV  = "DEV"
    }

    stages {

        stage('Cleanup Workspace') {
            steps {
                cleanWs()
                sh """
                echo "Cleaned Up Workspace for ${APP_NAME}"
                """
            }
        }

        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    userRemoteConfigs: [[url: 'https://github.com/spring-projects/spring-petclinic.git']]
                ])
            }
        }

        stage('Code Build') {
            steps {
                 sh 'mvn install -Dmaven.test.skip=true'
            }
        }

        stage('Priting All Global Variables') {
            steps {
                sh """
                env
                """
            }
        }

    }
}



























