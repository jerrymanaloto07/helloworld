node {
    stage('Build') {
        echo 'Building...'
        echo "Job name is ${env.JOB_NAME}"
        echo "Build number is ${env.BUILD_NUMBER}"
        echo "Build ID is ${env.BUILD_ID}"
        echo "Build tag is ${env.BUILD_TAG}"
        echo "Jenkins URL is ${env.JENKINS_URL}"
        echo "Current node name is ${env.NODE_NAME}"
        echo "Workspace is ${env.WORKSPACE}"
        echo "CVS branch is ${env.CVS_BRANCH}"
        echo "Hash of git commit  is ${env.GIT_COMMIT}"
        echo "Git branch is ${env.GIT_BRANCH}"
        
        //echo env.MYTOOL_VERSION
        // Add your build commands here, e.g.,
        // sh 'npm install'
    }

    stage('Test') {
        echo 'Testing...'
        // Add your test commands here, e.g.,
        // sh 'npm test'
    }

    stage('Deploy') {
        echo 'Deploying...'
        // Add your deployment commands here, e.g.,
        // sh 'npm run deploy'
    }
}
