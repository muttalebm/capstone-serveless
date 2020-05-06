pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                dir("${env.WORKSPACE}/client"){
                    nodejs('node'){
                        sh "npm install"
                    }

                }

            }
        }
    }
}
