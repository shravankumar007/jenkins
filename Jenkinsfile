pipeline{
    agent any
    tools {nodejs "node"}
    environment {
        imageName = "shravan567/react_demo"
        registryCredential = 'shravan567'
        dockerImage = ''

    }
    stages{
        stage("Install Dependencies"){
            steps{
                sh "npm install"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }
        stage("Building Image")
        {
            steps{
                script{
                    dockerImage = docker.build imageName
                }
            }
        }
        stage("Deploy Image"){
            steps{
                script{
                    docker.withRegistry("https://registry.hub.docker.com",'docker-cred'){
                    dockerImage.push("${env.BUILD_NUMBER}")
                    }
                }
            }
        }
    }
}