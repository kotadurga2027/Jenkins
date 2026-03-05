pipeline {
    agent {label 'AGENT-1'} 
        environment {
            COURSE = 'jenkins'
        }
        parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'prod'], description: 'Select deployment environment')
        }
        stages{
            stage ("checkout"){
                step{
                    echo "this is checkout stage"
                }
           }
            stage ("build") {
                step{
                    echo "this is build stage"
                    script {
                        sh 'printenv'
                    }
                }
            stage ("deploy"){
                step {
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

           }
        }
        post {
            always {
                echo "This pipeline status will get here"
            }
            sucess {
                echo "pipeline executed sucessfully"
            }
            failure {
                echo "pipeline exection failed"
            }

        }
    

