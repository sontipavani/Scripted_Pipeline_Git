pipeline{
    agent none
    stages{
        stage('Non parallel stage'){
        agent {
            label "master"
        }
        steps{
            echo 'This stage will be executed first'
        }
        }
        stage('Run Tests'){
        parallel{
            stage('Test on Windows'){
            agent{
                label "node"
            }
            steps{
                echo 'Task on agent1'
            }
        }
            stage('Test on master'){
            agent{
                label 'master'
            }
            steps{
                echo 'Task on agent2'
            }
        }
        }
    }
    }
}
