//String cron_only_on_master = env.BRANCH_NAME == "master" ? "@daily" : ""

pipeline {
    // Guide book on Jenkins declarative pipelines
    // https://jenkins.io/doc/book/pipeline/syntax/
    agent {
        docker {
            image "python:3"
            label 'docker'
        }
    }
//    triggers {
//        cron(cron_only_on_master)
//    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh("python --version; which python; python -c 'import os; print(os)'")
                    sh ("env; pwd; hostname -A; hostname -f; hostname -I; uname -a")
                }
            }
        }
    }

//    options {
//        ansiColor('xterm')
//        timestamps()
//        timeout(time: 1, unit: 'HOURS')
//        disableConcurrentBuilds()
//        buildDiscarder(logRotator(numToKeepStr: '20'))
//    }
}
