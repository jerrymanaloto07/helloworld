
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
        echo "Current build number is ${currentBuild.number}"
        echo "Current build result is ${currentBuild.result}"
        echo "displayName is ${currentBuild.displayName}"
        echo "projectName is ${currentBuild.projectName}"
        echo "description is ${currentBuild.description}"
        echo "current build id is ${currentBuild.id}"
        echo "duration of the build in milliseconds is ${currentBuild.duration}"
        //echo "absolute url of build index page is ${currentbuild.absoluteUrl}"
        echo "build variables are ${currentBuild.buildVariables}"
        echo "keepLog is ${currentBuild.keepLog}"
        echo "scm.userRemoteConfigs are ${scm.userRemoteConfigs}"
        echo "scm.branches are ${scm.branches}"
        def scm_data = checkout scm
        
        // Accessing the attributes
        echo "SHA-1 hash of git commit: ${scm_data.GIT_COMMIT}"
        echo "Remote branch being built GIT_BRANCH: ${scm_data.GIT_BRANCH}"
        echo "GIT_URL is ${scm_data.GIT_URL}"
        echo "GIT_LOCAL_BRANCH is ${scm_data.GIT_LOCAL_BRANCH}"
        echo "GIT_PREVIOUS_COMMIT is ${scm_data.GIT_PREVIOUS_COMMIT}"
        echo "GIT_PREVIOUS_SUCCESSFUL_COMMIT is ${scm_data.GIT_PREVIOUS_SUCCESSFUL_COMMIT}"
        echo "GIT_COMMITTER_NAME is ${scm_data.GIT_COMMITTER_NAME}"
        echo "GIT_COMMITTER_EMAIL is ${scm_data.GIT_COMMITTER_EMAIL}"
        echo "GIT_AUTHOR_NAME is ${scm_data.GIT_AUTHOR_NAME}"
        echo "GIT_CHECKOUT_DIR is ${scm_data.GIT_CHECKOUT_DIR}"
        
        
        
        
        withEnv(['CUSTOM_VERSION=1.2.3']) {
            // Variables are available only within this block
            echo "The version is ${env.CUSTOM_VERSION}"
        }
        
        //echo env.MYTOOL_VERSION
        // Add your build commands here, e.g.,
        // sh 'npm install'
    }
    stage('Deploy to c:\temp')
    {
        bat '''
            copy deploy_file.txt C:\\temp
            REM Verify the deployment
            dir C:\\temp
        '''
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
