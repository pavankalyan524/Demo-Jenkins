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
                
                sshagent(['privatekey']){

                    sh '''
                    ssh -o StrictHostKeyChecking=no ubuntu@54.167.25.250 <<EOF
			if [ ! -d "/home/ubuntu/Demo-Jenkins/.git" ]; then 
			   git clone https://github.com/pavankalyan524/Demo-Jenkins.git /home/ubuntu/Demo-Jenkins
 			fi
			cd /home/ubuntu/Demo-Jenkins/
                        git pull origin main
                    EOF
                    '''
                }
            }
        }
    }
}
