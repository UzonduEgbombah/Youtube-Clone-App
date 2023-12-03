
# Single Repo for both CI and CD

pipeline {
    agent any

    tools{
        jdk 'jdk17'
        nodejs 'node16'
    }
	
    // environment {
    //     DOCKERHUB = "asa96"
    //     APP_NAME = "flask-app"
    //     IMAGE_TAG = "${BUILD_NUMBER}"
    //     IMAGE_NAME = "${DOCKERHUB}" + "/" + "${APP_NAME}"
    //     REGISTRY_CREDS = "dockerhub-auth"
    // }
				
    stages {
	
        stage('Cleanup Workspace'){
            steps {
                script {
                    cleanWs()
                }
            }
        }
		
        stage('Code Checkout'){
            steps {
                git credentialsId: 'github-auth', 
                url: 'https://github.com/saeedalig/youtube-clone-app.git',
                branch: 'main'
            }
        }
		
        // stage('Build Docker Image'){
        //     steps {
        //         script{
        //             docker_image = docker.build "${IMAGE_NAME}"
        //         }
        //     }
        // }
		
        // stage('Push Docker Image'){
        //     steps {
        //         script{
        //             docker.withRegistry('', REGISTRY_CREDS ){
        //                 docker_image.push("${BUILD_NUMBER}")
        //                 docker_image.push('latest')
        //             }
        //         }
        //     }
        // } 
		
        // stage('Delete Docker Images'){
        //     steps {
        //         sh "docker rmi ${IMAGE_NAME}:${IMAGE_TAG}"
        //         sh "docker rmi ${IMAGE_NAME}:latest"
        //     }
        // }
		
		// stage('Update k8s deployment file'){
        //     steps {
        //         sh "cat deployment.yaml"
        //         sh "sed -i 's/${APP_NAME}.*/${APP_NAME}:${IMAGE_TAG}/g' deployment.yaml"                
        //         sh "cat deployment.yaml"
        //     }
        // }
        
        // stage('Push the changed deployment file to GitHub') {
        //     steps {
        //         script {
        //             sh """
        //             git config --global user.name "saeed"
        //             git config --global user.email "saeed@gmail.com"
        //             git add deployment.yaml
        //             git commit -m 'Updated the deployment file'
        //             """
        //             withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
        //                 sh 'git remote set-url origin https://$USER:$PASS@github.com/saeedalig/k8s-manifest.git'
        //                 sh 'git push origin main'
        //             }
        //         }
        //     }
        // }
    }
}