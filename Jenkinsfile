pipeline {
    agent {
        docker {
            image 'node:21-alpine'
        }
        parameters {
            string(name: 'NAME', defaultValue: 'M. Jenkins', description: 'qui est-ce ?')
            text(name: 'TEXT', defaultValue: 'un texte', description: 'une description')
            booleanParam(name: 'TOGGLE', defaultValue: true, description: 'true or false')
            choice(name: 'CHOICE', choices:['un', 'deux', 'trois'], description: 'liste')
            password(name: 'PASSWORD', description: 'un mot de pass')
        }
    }
    options { 
        timeout(time: 1, unit: "HOURS")
    }
    stages{
        stage('build'){
            options { 
                timestamps()
            }
            steps{
                sh 'npm -v'
                echo "NAME: ${ NAME }"
                echo "TEXT: ${ TEXT }"
                echo "TOGGLE: ${ TOGGLE }"
                echo "CHOICE: ${ CHOICE }"
                echo "PASSWORD: ${ PASSWORD }"
            }
       
          
    }
    post {
        always {
            echo 'always !'
        }
        success {
            echo 'success !'

        }
    }
}