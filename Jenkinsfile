properties([parameters([string(defaultValue: 'Hello', 
	description: 'How should I greet the world?', 
	name: 'Greeting')]
	)])

node {
    stage('Build') {
        def scm_data = checkout scm
		if (scm_data.branches?.contains('master'))
		{
			echo "Branch is master"
		}
		else
		{
			echo "Branch is not master"
		}
        echo "${params.Greeting} World"
        echo 'Building...'
        echo "Job name is ${env.JOB_NAME}"
        echo "Build number is ${env.BUILD_NUMBER}"
        echo "Build ID is ${env.BUILD_ID}"
        echo "Build tag is ${env.BUILD_TAG}"
        echo "Jenkins URL is ${env.JENKINS_URL}"
        echo "Current node name is ${env.NODE_NAME}"
        echo "Workspace is ${env.WORKSPACE}"
        echo "Ci is ${env.CI}"
        echo "Build number is ${env.BUILD_NUMBER}"
        echo "Build ID is ${env.BUILD_ID}"
        echo "Job name is ${env.JOB_NAME}"
        echo "Build tag is ${env.BUILD_TAG}"
        echo "Executor Number is ${env.EXECUTOR_NUMBER}"
        echo "Build url is ${env.BUILD_URL}"
        echo "Job url is ${env.JOB_URL}"
        echo "Current build number is ${currentBuild.number}"
        echo "displayName is ${currentBuild.displayName}"
        echo "projectName is ${currentBuild.projectName}"
        echo "current build id is ${currentBuild.id}"
        echo "duration of the build in milliseconds is ${currentBuild.duration}"
        //echo "absolute url of build index page is ${currentbuild.absoluteUrl}"
        echo "keepLog is ${currentBuild.keepLog}"
        echo "scm.userRemoteConfigs are ${scm.userRemoteConfigs}"
        echo "scm.branches are ${scm.branches}"
        
        // Accessing the attributes
        echo "SHA-1 hash of git commit: ${scm_data.GIT_COMMIT}"
        echo "Remote branch being built GIT_BRANCH: ${scm_data.GIT_BRANCH}"
        echo "GIT_URL is ${scm_data.GIT_URL}"
        echo "GIT_PREVIOUS_COMMIT is ${scm_data.GIT_PREVIOUS_COMMIT}"
        echo "GIT_PREVIOUS_SUCCESSFUL_COMMIT is ${scm_data.GIT_PREVIOUS_SUCCESSFUL_COMMIT}"
        
        
        
        
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
            copy hello.sh C:\\temp
            REM Verify the deployment 
            dir C:\\temp
			type c:\\temp\\hello.sh
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
		emailext (
                subject: "${currentBuild.result}: Job ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: """
                    Job: ${env.JOB_NAME} (${env.BUILD_NUMBER})
                    Status: ${currentBuild.result}
                    See the console output here: ${env.BUILD_URL}
                """,
                to: "developer@example.com",
                // Conditional triggers for different build states
                // Always send the email, but use different configurations if needed
                attachmentsPattern: '**/target/*.jar', // Example of attaching build artifacts
                presendScript: '$DEFAULT_PRESEND_SCRIPT'            )
    }
}
