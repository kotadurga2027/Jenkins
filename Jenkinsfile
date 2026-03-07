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
                        '''
                        print "hello this is build stage"
                        echo 'we will go to write pipeline for catalogue'

                        '''

                    }

                }

            }
            stage ('test') {
                steps {
                    script {
                        '''
                        print "hello this is test stage"
                        echo 'we will go to write pipeline for catalogue'

                        '''

                    }

                }

            }
            stage ('deploy') {
                steps  {
                    script {
                        '''
                        print "hello this is deploy stage"
                        echo 'we will go to write pipeline for catalogue'

                        '''

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