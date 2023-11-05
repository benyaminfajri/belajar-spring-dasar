pipeline{
    agent none

    stages{
        stage("prepare"){
            agent {
                node{
                    label "linux && java11"
                }
            }
            steps{
                echo("Start job ${env.JOB_NAME}")
                echo("Start In Node ${env.NODE_NAME}")
                echo("Start build ${currentBuild.fullDisplayName}")
            }
        }
        stage("build"){
            agent {
                node{
                    label "linux && java11"
                }
            }
            steps{
                script{
                    for(int i =0; i<=10; i++){
                        echo("Scripts ${i}")
                    }
                }
                echo "Start Building"
                sh("./mvnw clean compile test-compile")
                echo "Finish building"

            }
        }
        stage("test"){
            agent {
                node{
                    label "linux && java11"
                }
            }
            steps{
                script{
                    def data = ["writer":"benz", "book":"hopkins"]
                    writeJSON(file: "myjson.json",json: data)
                }
                echo "I am Testing"
                sh("./mvnw test")
                echo "Finish Testing"
                
            }
        }
        stage("deploy"){
            agent {
                node{
                    label "linux && java11"
                }
            }
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