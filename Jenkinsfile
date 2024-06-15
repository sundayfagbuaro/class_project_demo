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
    }
}