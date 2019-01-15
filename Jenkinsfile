import groovy.json.JsonSlurper
def fetchUrl = 'http://192.168.1.11:8080/view/all/job/jenkins%20rest%20api%20test/job/master/lastSuccessfulBuild/api/json'
def response

pipeline {
    agent any 
    stages {
        stage('Jenkins REST') {
            steps {
                script {
                    response = sh(returnStdout: true, script: "curl -s  -H \"Authorization: Basic dXNlcjphZG1pbg==\" -H \"Accept: application/json\" -X GET ${fetchUrl}").trim()
                    def jsonSlurper = new JsonSlurper()
                    def object = jsonSlurper.parseText("${response}")
                    def version = object.displayName
                    echo 'printing..'
                    echo version
                }
            }
        }

        stage('Copy source') {
            steps {
                sh 'echo "shastije"'
            }
        }
    }
}
