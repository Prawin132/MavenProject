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
                    userremoteConfigs: [[url:'https://github.com/Prawin132/MavenProject.git']]
                ])
            }
        }
        
        stage('build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                echo "building...."
            }
        }

        stage('test'){
            steps{
                sh 'mvn test'
                echo "testing.."
            }
        }
    }
}
