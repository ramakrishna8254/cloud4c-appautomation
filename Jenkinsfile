pipeline{
	agent any
	   stage('Checkoutcode'){
		   steps{
       git 'https://github.com/ramakrishna8254/cloud4c-appautomation.git'}
  }
}
 stage('Build'){
        nodejs(nodeJSInstallationName: 'nodejs16.19.0'){
        sh "npm install"
    }
    }
