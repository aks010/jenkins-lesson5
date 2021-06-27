node('master') {
    stage("Fetch Source Code") {
        cleanWs()
        git 'https://github.com/aks010/jenkins-lesson5'
    }
    
    dir('.') {
        printMessage('Running Pipeline')
        stage("Testing") {
          sh 'ls -la'
            sh 'python3 test_functions.py'
        }
        stage("Deployment") {
            if (env.BRANCH_NAME == 'master') {
                printMessage('Deploying the master branch')
            } else {
                printMessage("No deployment for branch [${env.BRANCH_NAME}]")
            }
            
        }
        printMessage('Pipeline Complete')
    }
}

def printMessage(message) {
    echo "${message}"
}
