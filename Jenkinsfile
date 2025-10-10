properties([parameters([string(defaultValue: 'Hello', 
	description: 'How should I greet the world?', 
	name: 'Greeting')]
	)])

node {
    stage('Build') {
        def scm_data = checkout scm
		echo "Building Pull Request #${env.CHANGE_ID}"
        echo "Source Branch: ${env.CHANGE_BRANCH}"
        echo "Target Branch: ${env.CHANGE_TARGET}"
            // Check out the code for the PR
        echo "Job name is ${env.JOB_NAME}"
        echo "Build number is ${env.BUILD_NUMBER}"
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

    stage('Deploy') {
        	echo 'Deploying...'
        // Add your deployment commands here, e.g.,
        // sh 'npm run deploy'
		emailext (
                subject: "Job ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: """
                    Job: ${env.JOB_NAME} (${env.BUILD_NUMBER})
                """,
                to: "developer@example.com",
                // Conditional triggers for different build states
                // Always send the email, but use different configurations if needed
                attachmentsPattern: '**/target/*.jar', // Example of attaching build artifacts
                presendScript: '$DEFAULT_PRESEND_SCRIPT'            )
    }
}
