@Library('my-first-shared-library') _

pipeline{

    agent any

    tools{
        maven 'MAVEN3.9'
    }

    stages{

        stage('Code Checkout'){
            steps{
                checkoutCode("https://github.com/svishal16/project-3.git")
            }
        }

        stage('Build Code'){
            steps{
                buildMavenProject()
            }
        }

        stage('Code Test'){
            steps{
                runTests()
            }
        }

    }

    post{
        always{
            script{
                notifyResults(currentBuild.currentResult)
            }
        }
    }

}