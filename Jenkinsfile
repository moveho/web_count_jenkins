node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/moveho/web_count_jenkins.git'
    }

    stage('Build image') {
       dockerImage = docker.build("moveho/web_count:1.0")
    }

 stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}

