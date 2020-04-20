pipeline {
    agent any
    triggers {
        upstream(upstreamProjects: "Wordpress-Dev", threshold: hudson.model.Result.SUCCESS)
    }
    parameters {
        string(name: 'IMAGE', defaultValue: 'latest', description: 'Name of the docker image')

        choice(name: 'ENVIRONMENT', choices: ['staging', 'production'], description: 'Select the deployment environment')
    }
    stages {
        stage('Hello') {
            steps {
                echo "Image: ${params.IMAGE}"
                echo "Environment: ${params.ENVIRONMENT}"
            }
        }
    }
}