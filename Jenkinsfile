pipeline {
	agent any

	stages {
		stage("build") {
			steps {
				docker build .
			}
		}
		stage("test") {
			steps {
				curl http://localhost:80
			}
		}
	}
}
