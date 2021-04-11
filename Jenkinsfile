pipeline{
    agent any
    environment{
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('bitbucket')
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
            steps{
                echo "Testing the project"
            }
        }             
    }
}