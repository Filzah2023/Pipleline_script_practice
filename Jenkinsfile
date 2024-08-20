pipeline {
    agent none

    stages {
        
    stage ('Non-parallel stage') {
            agent {
                    label "Built-In "
              }
            steps {
                echo 'This stage will be executed first'
            }
        }

        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                        echo "Task1 on Agent";
                    }
                }
                stage('Test on Built-In') {
                    agent {
                        label "Built-In "
                    }
                    steps {
                        echo "task1 on Built-In ";
                    }
                }
            }
        }
    }
}
