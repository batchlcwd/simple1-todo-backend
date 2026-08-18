pipeline {
agent any 

environment{
    PROJECT_NAME="todo-backend"
    DOCKER_IMAGE="batchlcwd/simple-todo-backend"
    DOCKER_TAG="${BUILD_NUMBER}"
}

stages{

stage("Welcome stage")
{
    steps{
        echo 'Hello, Pipeline for "${PROJECT_NAME}" started...'
        echo 'Build Numer is "${BUILD_NUMBER}"'
    }
}


}
}