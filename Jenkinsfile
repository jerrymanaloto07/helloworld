
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
        echo "Branch name is ${env.BRANCH_NAME}"
        echo "Is branch primary? ${env.BRANCH_IS_PRIMARY}"
        echo "Change ID is ${env.CHANGE_ID}"
        echo "Change url is ${env.CHANGE_URL}"
        echo "Change title is ${env.CHANGE_TITLE}"
        echo "Change author is ${env.CHANGE_AUTHOR}"
        echo "Change author email is ${env.CHANGE_AUTHOR_EMAIL}"
        echo "Ci is ${env.CI}"
        echo "Build number is ${env.BUILD_NUMBER}"
        echo "Build ID is ${env.BUILD_ID}"
        echo "Job name is ${env.JOB_NAME}"
        echo "Build tag is ${env.BUILD_TAG}"
        echo "Executor Number is ${env.EXECUTOR_NUMBER}"
        echo "Build url is ${env.BUILD_URL}"
        echo "Job url is ${env.JOB_URL}"
        
        
        
        withEnv(['CUSTOM_VERSION=1.2.3']) {
            // Variables are available only within this block
            echo "The version is ${env.CUSTOM_VERSION}"
        }
        
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
