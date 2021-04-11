pipeline{
    agent any
    environment{
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('bitbucket')
    }
    tools {
        maven 'amit-maven'
    }
    parameters {
        choice( name: 'Version', choices: ['1.0.1','1.0.2','1.0.3'] , description: 'some crap' )
        booleanParam (name: 'execute', defaultValue: false, description: 'some dude')
    }
    stages{
        stage("get source code"){
            steps{
                echo "getting file from github ${SERVER_CREDENTIALS}"
            }
        }
        stage("build"){
            steps{
                echo "buiding the project with version ${NEW_VERSION}"
            }
        }
        stage("deploy"){
            steps{
                echo "Deploying the project"
            }
        }     
        stage("test"){
            when{
                expression {
                    params.execute
                }
            }
            steps{
                echo "Testing the project with ${params.Version}"
            }
        }             
    }
}