pipeline {
    agent any 
    stages {
        stage("Lint HTML"){
            steps {
                sh "tidy -q -e *.html"
            }
        }
        stage("Upload to AWS") {
            steps {
                withAWS(region:'us-west-2',credentials:'27c49126-b276-44b5-a364-1959d209411d') {
                    s3Upload file:'index.html', bucket:'yinkin'
                }
            }
        }
    }
}
