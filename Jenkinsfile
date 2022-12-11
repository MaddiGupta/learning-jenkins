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

pipeline{
    agent any

        stages{
            stage('one'){
                steps {
                    echo 'ONE'
                }

            }
            stage('two'){
                when{
                    expression {
                        BRANCH_NAME == "master"
                    }
                }
                steps{
                    echo 'TWO'
                }
            }
        }
}