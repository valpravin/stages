import java.text.SimpleDateFormat

//ENTIRE GLOBAL FUNCTION FLOW
def branchName = env.BRANCH_NAME.toLowerCase() //make lowercase because startsWith is case sensitive


if (branchName.startsWith('main')) {
	node('mesos') {
	stage('Starting Release Task')
	
	askApproval()
	}
	}

def askApproval() {
	stage('Stop Appoval') {
		timeout(time: 10, unit: 'MINUTES') {
			input message: "OK to Stop the Apps ?", ok: 'Approve', submitter: approver
		}
	}
}