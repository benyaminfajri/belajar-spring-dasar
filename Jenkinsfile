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
            }
        }
        stage("test"){
            steps{
                echo "I am Testing"
                sh "error"
            }
        }
        stage("deploy"){
            steps{
                echo "I am Deploying"
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