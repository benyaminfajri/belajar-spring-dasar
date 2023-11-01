pipeline{
    agent {
        node{
            label "linux && java11"
        }
    }
    stages{
        stage("build"){
            steps{
                echo "Start Building"
                sh("./mvnw clean compile test-compile")
                echo "Finish building"

            }
        }
        stage("test"){
            steps{
                echo "I am Testing"
                sh("./mvnw test")
                echo "Finish Testing"
                
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