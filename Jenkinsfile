pipeline {
    agent any
    
    tools{
        maven 'maven-3.6.0'
    }

    stages{
        stage('Code Checkout'){
            steps{
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    userremoteConfigs: [[
                        credentialsId: 'praveen_git_repo'
                        url:'https://github.com/Prawin132/MavenProject.git']]
                ])
            }
        }
        
        stage('build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                echo "Building...."
            }
        }

        stage('test'){
            steps{
                sh 'mvn test'
                echo "Testing..."
            }
        }
    }
}
