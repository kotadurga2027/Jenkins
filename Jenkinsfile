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
    

