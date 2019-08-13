#!/usr/bin/groovy

pipeline {
    agent any

    options {
        disableConcurrentBuilds()
    }

    stages {

        stage("Build") {
            steps { buildApp() }
		}

        stage("Deploy - Dev") {
            steps { deploy('dev') }
		}

	}
}


// steps
def buildApp() {
	dir ('templates/' ) {
		def appImage = docker.build("hands-on-jenkins/myapp:${BUILD_NUMBER}")
	}
}

