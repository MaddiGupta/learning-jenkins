pipeline{
    agent any

    stages{

        stage('TEST1'){
            steps{
                echo 'Test1'
            }
        }

        stage('TEST2'){
             steps{
                 echo 'Test2'
             }
        }
    }
}

post {
 fixed {
  echo "Hello"
 }
 failed{
  echo "failed state"
 }
 cleanup{
  echo "common steps"
 }
}