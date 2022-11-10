pipeline {
    agent any
    stages {
        stage('OWASP Dependency Check') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML ', odcInstallation: 'OWASP'
            }
            post {
                success {
                    dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
                }
            }
        }
}