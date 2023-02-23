pipeline{
	agent any
	stages{
	   stage('Checkoutcode'){
		   steps{
       git 'https://github.com/ramakrishna8254/cloud4c-appautomation.git'}
  }
 stage('Build * Sonar Analysis'){
	 steps{
        nodejs(nodeJSInstallationName: 'nodejs16.19.0'){
        sh "sudo npm install"
		withSonarQubeEnv('sonarserver'){
		sh "npm install --save-dev mocha chai"
		sh "npm run test"
		sh "npm run coverage-lcov"
		sh "npm install sonar-scanner"
		sh "npm run sonar"
		}
    }
    }
stage('UploadArtifactintoNexus'){
	steps{
	nodejs(nodeJSInstallationName: 'nodejs16.19.0'){
	    sh "npm publish"
    }
}
	}
}
}
}
