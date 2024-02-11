pipeline{
    agent any
    environment {
        MY_VAR = 'une variable'
        MY_NUMBER = 123
    }
    stages{
        stage('build'){
            steps{
                echo "BRANCH_NAME : ${ env.BRANCH_NAME }"
                echo "BRANCH_IS_PRIMARY : ${ env.BRANCH_IS_PRIMARY }"
                echo "CI : ${ env.CI }"
                echo "BUILD_NUMBER: ${env.BUILD_NUMBER }"
                echo "JENKINS_URL : ${env.JENKINS_URL }"
                echo "MY_VAR : ${ env.MY_VAR }"
                echo "MY_NUMBER : ${ env.MY_NUMBER }"
                sh 'printenv'
            }
       
          
    }
}