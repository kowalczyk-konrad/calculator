pipeline {
    agent any
    stages {
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }
        stage("Unit Test") {
        steps {
            sh "./gradlew test"
            }
        }
	stage("Code coverage") {
	steps {
		sh "./gradlew jacocoTestReport"
		publishHTML (target: [
			reportDir: 'build/reports/jacoco/test/html',
			reportFIles: 'index.html',
			reportName: "JaCoCo Report"
			])
		sh "./gradlew jacocoTestCoverageVerification"
		}
	}
    }
}
