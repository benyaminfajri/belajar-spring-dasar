pipeline{
    agent {
        node{
            label "linux && java11"
        }
    }
    stages{
        stage("build"){
            steps{
                echo "I am Building"
                sleep (5)
                echo "I am Building 2"
                echo "I am Building 3"

            }
        }
        stage("test"){
            steps{
                echo "I am Testing"
                sleep (5)
                echo "I am Testing 2"
                echo "I am Testing 3"
                
            }
        }
        stage("deploy"){
            steps{
                echo "I am Deploying"
                sleep (5)
                echo "I am Deploying 2"
                echo "I am Deploying 3"
            }
        }
        
    }
    post{
        always{
            echo 'I always excecute'
        }
        regression{
            echo "I am on Regression"
        }
        fixed {
            echo "I am on fixed"
        }
        success{
            echo "I am on success"
        }
        failure{
            echo "I am on failure"
        }
        cleanup{
            echo "I am on cleanup"
        }
    }
}