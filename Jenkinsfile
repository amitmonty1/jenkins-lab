def gv
pipeline{
    agent any
    tools{
        maven 'amit-maven'
    }
    environment{
        my_revision = '1.2.1'
    }
    parameters{
        choices(name: "version", choice: ['1.0.1','1.0.2','1.0.3'], description: 'choices for version')
        booleanParam(name: "checkflag", defaultValue: true)
    }
    stages{
        stage("get code"){
            steps{
                script{
                  gv = load "script.groovy"
                  gv.build()
                }
            }
        }
        stage("build code"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("deploy"){
            steps{
                echo "deploying the ${my_revision} to prod"
            }
        }
    }
    post{
        success{
           echo "success"
        }
        always{
            echo "always"
        }
        failure{
            echo "failure"
        }
    }
}