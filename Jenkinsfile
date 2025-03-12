pipeline{
    agent any
    
    stages{
        stage ("Checkout Code"){
            steps{
                git branch: "main", url: "https://github.com/pavankalyan524/Demo-Jenkins.git"
            }
        }
        
        stage("Deploying to ec2"){
            steps{
                
                sshagent(['publickey']){

                    sh '''
                    ssh -o StrictHostKeyChecking=no ubuntu@54.167.25.250 << EOF
                        cd /home/ubuntu/
                        git pull origin main
                    EOF
                    '''
                }
            }
        }
    }
}
