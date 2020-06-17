##  Jenkins file to deploy the hello-world image


```sh
pipeline {
    agent none
    stages {
        stage('Test hello-world') {
            agent {
                docker { image 'hello-world' }
            }
            steps {
                sh 'echo hello-world > echofile.txt'
            }
        }

    }
}

```
