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

pipeline{
    agent any
        tools {
            maven 'maven'
        }
        stages{
            stage('Maven Version'){
                input {
                    message "Should we continue?"
                    ok "Yes, we should."
                    submitter "alice,bob"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                    }
                }
            steps {
                sh 'mvn --version'
            }
            }
        }
}