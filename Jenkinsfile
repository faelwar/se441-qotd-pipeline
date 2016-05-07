stage "DEV-QA"

node {
	git 'https://github.com/faelwar/se441-qotd.git'
	
	def gradleHome = tool 'Gradle 2.11'
	bat "${gradleHome}\\bin\\gradle.bat assemble uploadArchives test sonarqube"
	
	step([$class: 'ArtifactArchiver', artifacts: '**/*.war', fingerprint: true])
}