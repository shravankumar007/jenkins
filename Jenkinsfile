pipeline{
    agent any
    tools {nodejs "node"}
    stages{
        stage("Install Dependencies"){
            steps{
                sh "npm install"
            }
        }

        stages("Test"){
            steops{
                sh "npm test"
            }
        }
    }
}