def gv 
pipeline{
    agent any
    environment{
        newversion = '1.3.5'
    }
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
                script{
                    gv = load "script.groovy"
                    gv.build()
                }
            }
        }
        stage("build"){
            steps{
              echo "building"
              def mvHome = tool name: 'amit-maven', type: 'maven'
              sh "${mvHome}/bin/mvn package"
 
              
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
              echo "deploying ${newversion}"
            }
        }                        
    }

}