pipeline {
    agent {label 'AGENT-1'}
        environment {
            NAME = 'kotadurga'
            AGE = '28'
            ROLE = 'Devops Engineer'
        }
        parameters {
            choice(name: 'ENVIRONMENT', choices: ['dev','qa','prod'], description: 'select dployment environment')
            string(name: 'PERSON', defaultValue: 'Mr kotadurga', description: 'Who should I say hello to?')
            text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
            booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
            choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
            password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
        }
        options {
            timeout(time: 10, unit: 'SECONDS')
            disableConcurrentBuilds()
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
                        sleep 10
                    }
                }
            }
            stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                }
            }
            stage ('deploy'){
                input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr kotadurga', description: 'Who should I say hello to?')
                }
            }
           
            }
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
            echo "this is always show the status of pipeline"
            deleteDir()
        }
        success {
            echo "pipeline execution is success"
        }
        failure {
            echo "pipeline execution is failed"
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

