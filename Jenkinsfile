pipeline{
    agent{
        label "JENKINS-AGENT-1"
    }
    stages{
        stage("Git Checkout"){
            steps{
                git branch: 'main', credentialsId: 'git-hub', url: 'https://github.com/sundayfagbuaro/class_project_demo.git'
            }
        }
        stage('Building Docker Image') {
            steps{
                script{
                    echo "Building Docker Image"
                    sh 'docker build -t sundayfagbuaro/flask-class-demo:v1.0 .'
                }
            }
        }
    //    stage('Pushing image to docker hub'){
    //        steps{
    //            script{
    //                withCredentials([string(credentialsId: 'docker-token-newest', variable: 'docker-pass-demo')]) {
    //                    sh 'docker login -u sundayfagbuaro -p $docker-pass-demo'
    //                }
    //                sh 'docker push sundayfagbuaro/flask-class-demo:v1.0'
    //            }
    //        }
    //    }

        stage('Push Image to Docker Hub'){
            steps{
                echo 'Pushing image to docker hub'
                withCredentials([string(credentialsId: 'docker-pwd', variable: 'DockerHubPwd')]) {
                sh 'docker login -u sundayfagbuaro -p ${DockerHubPwd}' 
                }
                sh 'docker push sundayfagbuaro/flask-class-demo:v1.0'
            }
        }

    }
}