pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Performance Smoke Test') {
            when {
                changeRequest()
            }

            steps {
                bat '''
                C:\\apache-jmeter-5.4.2\\bin\\jmeter.bat -n ^
                -t Ship_Registration_21_08_2026.jmx ^
                -l result.jtl
                '''
            }
        }
    }
}
