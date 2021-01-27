pipeline {
    agent any
    
    tools{
        maven 'maven-3.6.0'
    }

    stages{
        stage('build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                echo "building...."
            }
        }

        stage('test'){
            steps{
                echo "testing..."
            }
        }
    }
}
