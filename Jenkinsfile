pipeline{

    agent{
        label "jenkins-agent"
    }
    
    tools{
        jdk "Java17"
        maven "Maven3"
    }
    stages{
        stage("Cleanup Workspace"){
            steps{
                cleanWs()
            }
            
        }
    
        stage("Checkout from SCM"){
            steps{
                git branch: 'main', url: 'https://github.com/dmancloud/complete-prodcution-e2e-pipeline.git'
            }
        }

        stage("Build application"){
            steps{
                sh 'mvn clean package'
            }
        }

        stage("Test application"){
            steps{
                sh 'mvn test'
            }
        }
    }
}