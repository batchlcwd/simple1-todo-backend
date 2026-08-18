pipeline {
agent any 

environment{
    PROJECT_NAME="todo-backend"
    DOCKER_IMAGE="batchlcwd/simple-todo-backend"
    DOCKER_TAG="${BUILD_NUMBER}"
}

stages{

stage("Checkout"){

        steps{
            checkout scm 
            echo "checkout successful"
            echo "Testing from github..."
        }

}



stage("Welcome stage")
{
    steps{
        echo 'Hello, Pipeline for "${PROJECT_NAME}" started...'
        echo 'Build Numer is "${BUILD_NUMBER}"'
    }
}


}
}