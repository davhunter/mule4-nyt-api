pipeline {
	agent any
	stages {
		stage('Build') {
			environment {
				ANYPOINT_CREDENTIALS = credentials('CloudHub')
				NYT_API_KEY = credentials('NYT-API-KEY')
			}
			steps {
				sh 'mvn clean package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Dhttp.port=8083 -DnytApiKey=$NYT_API_KEY'
			}
		}
	}
}