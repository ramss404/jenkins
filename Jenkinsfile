pipeline {
    agent any
environment {
    brnchname="hotfix/ANLYS-3232"
}
    stages {
        stage ('scm') {
            steps {
                script {
                    echo "given branch is ${brnchname}"
                    
                    if (brnchname.startsWith("private") || brnchname.startsWith("hotfix") || brnchname.startsWith("feature")) {
                        
                        echo "branch starts with in branch - ${brnchname}"
                        if (brnchname =~ /ANLYS-.+/) {
                            echo "branch name contains ANLYS in branch - ${brnchname}"
                        }
                    }
                    else {
                        echo "branch not started with hotfix/feature/private"
                    }
                        
                }
            }
        }
        stage ('validation') {
            steps {
                script {
                    
                    if (brnchname =~ /release-.+|hotfix\/.+/)  {    
                        echo "branch name contains ${brnchname}"
                        
                        if (brnchname =~ /ANLYS-.+/) {
                            echo "branch name contains ANLYS"
                        }
                    } 
                    else {
                    echo "branch name does not valid"
                    }
                }    
            }
        }
    }
}
