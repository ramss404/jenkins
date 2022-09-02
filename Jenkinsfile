def branch_nem = scm.branches[0].name
if (branch_nem.contains("*/")) {
    branch_nem = branch_nem.split("\\*/")[1]
    }
echo branch_nem


pipeline {
    agent any
environment {
    brnchname="ANLYS-3232"
}
    stages {
        stage ('scm') {
            steps {
                script {
                    
                    echo "br is ${branch_nem}"
                }    
            }
        }
        stage ('validation') {
            steps {
                script {
                    sh '''
                        
                       '''
                    
                    if (brnchname =~ /release-.+|hotfix\/.+|\/ANLYS-.+/)  {    
                        echo "branch name contains ${brnchname}"
                    } 
                    else {
                    echo "branch name does not contain private"
                    }
                }    
            }
        }
    }
}
