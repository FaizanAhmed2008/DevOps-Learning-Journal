# Jenkins Pipelines

## What is a Pipeline?
- A suite of plugins supporting the implementation and integration of **Continuous Delivery** pipelines.
- Defined in a text file named `Jenkinsfile` stored in version control (Pipeline-as-Code).

## Declarative Pipeline Syntax

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                // sh 'npm install' or 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // sh 'npm test' or 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // sh 'docker build ...' or 'kubectl apply ...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished execution.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
```

## Key Directives
- **`pipeline`**: Top-level block defining the Declarative Pipeline.
- **`agent`**: Specifies where the pipeline executes (`any`, `none`, or specific `docker`/`node`).
- **`stages`**: Contains all the individual stages to execute sequentially.
- **`stage`**: Groups steps into a named logical phase (e.g., Build, Test, Deploy).
- **`steps`**: The actual commands/actions executed within a stage (e.g., `sh`, `echo`).
- **`post`**: Actions that run after stages complete based on build status (`success`, `failure`, `always`).

## Notes
- Store `Jenkinsfile` in the root of your Git repository for automated pipeline triggers.
- Multi-branch pipelines automatically discover branches and build matching Jenkinsfiles.
