node('HRMS QA') {
	stage('git'){
		git 'https://github.com/ArchanaWikky/game-of-life'
	}
	stage('build'){
		sh 'mvn clean package'
	}
	stage('archiveArtifacts') {
		archiveArtifacts artifacts: 'gameoflife-web/target/*.war', followSymlinks: false
	}
	stage('testresults') {
		junit 'gameoflife-web/surefire-reports/*.xml'
	}
}