pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                dir("${env.WORKSPACE}/client"){
                    sh "npm install"
                }

            }
        }
    }
}
