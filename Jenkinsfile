def branch_nem = scm.branches[0].name
if (branch_nem.contains("*/")) {
    branch_nem = branch_nem.split("\\*/")[1]
    }
echo branch_nem


pipeline {
    agent any
environment {
    brnchname="${branch_nem}"
}
    stages {
        stage ('scm') {
            steps {
                script {
                    git branch: 'main', credentialsId: 'fbff5d5b-b0ab-4e5d-ad42-97c933e4773d', url: 'https://github.com/middesreenivasjayanthi/jenkins.git'
                    
                    echo "br is ${env.GIT_BRANCH}"
                }    
            }
        }
        stage ('validation') {
            steps {
                script {
                    if (brnchname == "origin/main") {
                    echo "branch name contains private"
                    } 
                    else {
                    echo "branch name does not contain private"
                    }
                }    
            }
        }
    }
}
