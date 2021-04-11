pipeline{
    agent any
    tools{
        maven 'amit-maven'
    }
    parameters{
        choice(name: 'Version',choices: ['1.2.1','1.2.2','1.2.3'], description: 'awdawd awdawd')
        booleanParam(name: 'flag', defaultValue: true)
    }
    stages{
        stage("get from repo"){
            steps{
              echo "getting from git"
            }
        }
        stage("build"){
            steps{
              echo "building"
            }
        }
        stage("test"){
            steps{
              echo "testing"
            }
        }
        stage("deploy"){
            when{
                expression{
                    params.flag
                }
            }
            steps{
              echo "deploying"
            }
        }                        
    }

}