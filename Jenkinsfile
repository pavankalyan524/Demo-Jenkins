pipeline{
    agent any
    
    stages{
        stage("FIrst checkout"){
            steps{
                git branch: "main", url : "https://github.com/pavankalyan524/Demo-Jenkins.git"
            }
        }
        stage("Second stage"){
            steps{
                echo "Code Checkout Successful"
            }
        }
        }
    }
}
