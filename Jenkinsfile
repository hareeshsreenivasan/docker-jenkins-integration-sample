pipeline{
    agent any
    stages {
        stage ('Build'){
            steps{
                sh 'printenv'
                sh 'docker build -t hareesh52/docker-jenkins-integration-sample:""$BUILD_ID"" .'
            }
        }
        stage ('Publish'){
            steps{
                withDockerRegistry([credentialsId:"docker-hub", url:""]){
                    sh 'docker push hareesh52/docker-jenkins-integration-sample:""$BUILD_ID""'
                    }
                }
            }
        }
    }