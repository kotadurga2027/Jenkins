pipeline {
    agent {label 'AGENT-1'}
        environment {
            NAME = 'kotadurga'
            AGE = '28'
            ROLE = 'Devops Engineer'
        }
        parameters {
            choice(name: 'ENVIRONMENT', choices: ['dev','qa','prod'], decsription: 'select dployment environment')
        }
        stages{
            stage ('checkout'){
                steps{
                    echo "this is checkout stage"
                }
            }
            stage ('build'){
                steps{
                    echo "this is build stage"
                    script{
                        sh 'printenv'
                    }
                }
            }
            stage ('deploy'){
                steps{
                    echo "this is deploy stage"
                    script{
                        if (environment == "dev") {
                            echo "Deploying to Dev"
                        } 
                        else {
                            echo "deploying in other env"
                        }                      

                    }
                }
            }
        }
    post {
        always {
            echo "this is always show the status of pipeline
        }
        success {
            echo "pipeline execution is success"
        }
        failure {
            echo "pipeline execution is failed"
        }
    }
}






/*
pipeline {
    agent {label 'AGENT-1'} 
        environment {
            COURSE = 'jenkins'
        }
        parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'prod'], description: 'Select deployment environment')
        }
        stages{
            stage ('checkout') {
                steps {
                    echo "this is checkout stage"
                    }
                } 
            stage ('build') {
                steps {
                    echo "this is build stage"
                    script {
                        sh 'printenv'
                        }
                    }
                }
            stage ('deploy') {
                steps {
                    echo "this is deploy stage"
                    script {
                        if (environment == "prod") {
                            echo "Deploying to Production"
                        } 
                        else {
                            echo "Deploying to Non-Production"
                    }
                }       
                    }
                }
            

           }
        post {
            always {
                echo "This pipeline status will get here"
            }
            success {
                echo "pipeline executed sucessfully"
            }
            failure {
                echo "pipeline exection failed"
            }
        }
}

*/   

