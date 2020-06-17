##  Jenkins file to deploy the hello-world image


```sh
pipeline {
    agent {
        docker { image 'hello-world' }
    }
    stages {
        stage('Test hello-world') {
            steps {
                echo 'testing  hello-world image'
            }
        }
    }
}

```
