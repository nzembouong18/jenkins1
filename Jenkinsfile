pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
        
        parameters {
            string(name: 'NAME', defaultValue: 'M. Jenkins', description: 'qui est-ce ?')
            text(name: 'TEXT', defaultValue: 'un texte', description: 'une description')
            booleanParam(name: 'TOGGLE', defaultValue: true, description: 'true or false')
            choice(name: 'CHOICE', choices:['un', 'deux', 'trois'], description: 'liste')
            password(name: 'PASSWORD', description: 'un mot de pass')
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
                sh 'java -version'
                echo "NAME: ${ NAME }"
                echo "TEXT: ${ TEXT }"
                echo "TOGGLE: ${ TOGGLE }"
                echo "CHOICE: ${ CHOICE }"
                echo "PASSWORD: ${ PASSWORD }"
            }
    
       }
    stage('Deploiement en production') {
        input{
            message "Voulez-vous déployer en production ?"
            ok "Oui, déployons."
            submitter "admin, devops"
            parameters {
                string(name: 'VERSION', defaultValue: 'latest', description: 'quelle version souhaitez-vous deployer ?')
            }
        }
        steps {
            echo "Déploiement de la ${ VERSION } en production."
        }
    }
    
    }
}