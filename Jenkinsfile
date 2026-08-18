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

stage("Test"){

steps{
    sh '''
    chmod +x ./mvnw
    ./mvnw test

    '''
}

}


stage("Build"){

steps{
    sh '''
    
    ./mvnw clean package -DskipTests

    '''
}

}



stage("Docker Build"){

steps{
    sh '''
   

    docker build \
    -t ${DOCKER_IMAGE}:${DOCKER_TAG} .

    
    

    '''
}
}



stage("Docker Push"){

steps{
 
    withCredentials([
        usernamePassword(
            credentialsId: 'dockerhub-credentials',
            usernameVariable: 'DOCKERHUB_USERNAME',
            passwordVariable: 'DOCKERHUB_PASSWORD'
        )
    ])
    {

        sh '''      

            echo "$DOCKERHUB_PASSWORD | docker login -u $DOCKERHUB_USERNAME --password-stdin"

            docker push ${DOCKER_IMAGE}:${DOCKER_TAG}

            docker image prune -af 
            
            docker images

        '''

    }

}



}




}


}