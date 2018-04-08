node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/pattaabhi/python-docker-app.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "manee2k6/vegas"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'Github-ID', url: 'https://hub.docker.com']) {
          sh 'docker tag manee2k6/vegas manee2k6/vegas:001'
          sh 'docker push manee2k6/vegas:001'
          sh 'docker push manee2k6/vegas:latest'
      }
    }
   
    stage('App deployed to Docker') {
     echo 'App deployed to Hub..'
    }

   
























}
