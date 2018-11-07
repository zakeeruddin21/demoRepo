pipeline {
    agent any
    stages {
        stage("Initialization") {
            steps {
                script {
                    echo BRANCH_NAME
                    String envChoices = ""
                    if(BRANCH_NAME == 'master') {
                      envChoices = "dev\nqa\n"
                    }
                    else if(BRANCH_NAME ==~ /release.*/) {
                      envChoices = "default\nacceptance\nperf\n"
                    }

                    properties([parameters([choice(choices: "${envChoices}", description: 'Master Pipeline Environments', name: 'ENV')])])

                }
            }
        }
    }
}
