pipeline {
    agent {lable 'SERVER-1'}
       /*  environment {
             appVersion = 

    
         } */
        options{
            disableConcurrentBuilds()
        }

        stages {
            stage ('build') {
                steps{
                    script {

                    }

                }

            }
            stage {
                steps ('test') {
                    script {

                    }

                }

            }
            stage {
                steps ('deploy') {
                    script {

                    }

                }  
            }
        }
        post {
            success {
                echo "pipeline execution is sucess"
            }
            failure {
                echo "pipeline execution is failed"
            }
        }

    }