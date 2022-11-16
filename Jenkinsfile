pipeline {
    agent any
    stages {
        stage('OWASP Dependency Check') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML --suppression JenkinsDependencyCheckTest-master/suppression.xml', odcInstallation: 'OWASP Dependency Check'
            }
            post {
                success {
                    dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
                }
		}
        }
    }
}