pipeline{
    agent{
        label 'linux'
    }
    stages{
        stage('checkout git'){
            steps{
                dir('vector'){
                    git branch: 'main', url: 'https://github.com/aspire87/vector-role.git'
                }
            }
        }
        stage('install dependencies'){
            steps{
                dir('vector'){
                    sh 'pip3 install -r requirements.txt'
                }
            }
        }
        stage('run molecule'){
            steps{
                dir('vector-role'){
                    sh 'molecule test'
                }
            }
        }
    }
}