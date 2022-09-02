def branch_nem = scm.branches[0].name
if (branch_nem.contains("*/")) {
    branch_nem = branch_nem.split("\\*/")[1]
    }
echo branch_nem


pipeline {
    agent any
environment {
    brnchname="release-20220902"
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
                        IN="bla@some.com;john@home.com"

                        mails=$(echo $IN | tr ";" "\\n")

                        for addr in $mails
                        do
                        echo "> [$addr]"    
                        done
                        '''
                    
                    if (brnchname =~ /release-.+|hotfix\/.+/)  {    
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
