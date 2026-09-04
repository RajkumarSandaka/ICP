pipeline {
agent any

```
stages {

    stage('Checkout') {
        steps {
            checkout scm
        }
    }

    stage('Performance Smoke Test') {
        steps {
            bat '''
            C:\\apache-jmeter-5.4.2\\bin\\jmeter.bat -n ^
            -t "%WORKSPACE%\\Ship_Registration_21_08_2026.jmx" ^
            -l "%WORKSPACE%\\result.jtl"
            '''
        }
    }
}

post {
    always {
        archiveArtifacts artifacts: '**/*.jtl', allowEmptyArchive: true
    }
}
```

}
