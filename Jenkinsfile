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
                    sh 'docker build -t flask-class-demo:v1.0 .'
                }
            }
        }
    }
}