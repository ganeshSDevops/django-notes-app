@Library('shared') _
pipeline{
    agent {label 'vinod'}
    stages{
        stage('hello'){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('code'){
            steps{
                script{
                    clone('https://github.com/ganeshSDevops/django-notes-app.git','dev')
                }
            }
        }
        stage('Build'){
            steps{
                script{
                    dockerbuild('notes-app','latest','ganeshsoneplus')
                }
            }
        }
        stage('Push IMG to Docker'){
            steps{
                script{
                    docker_push('notes-app','latest','ganeshsoneplus')
                }
            }
        }
        stage('Test'){
            steps{
                echo 'this is testing code'
                echo 'testing done'
            }
        }
        stage('Deploy'){
            steps{
                echo 'this is deploying code'
                sh 'docker compose up -d'
            }
        }
    }
}  
