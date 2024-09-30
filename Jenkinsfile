def gv
pipeline{
    agent any
    parameters{
        booleanParam(name:'ExecuteTest',defaultValue:'true', description:'')
        choice(name:'Version',choices:['1.1.0','1.2.0','1.3.0'], description:'')
    }
    stages{
        stage('init'){
            steps{
                script{
                  gv = load script.groovy
                }
            }
        }
        stage('Build'){
            when{
              expression{
                  Params.ExecuteTest
              }
            }
            steps{
                script{
                  gv.BuildApp()
            
                  }
                }
        }
        stage('Test'){
            steps{
                script{
                    gv.TestApp()
                }
            }
        }
        stage('Deploy'){
            steps{
                script{
                    gv.DeployApp()
                }
            }
        }
    }
} 
