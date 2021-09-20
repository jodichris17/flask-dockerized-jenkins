node {
   stage('Get Source') {
      // copy source code from local file system and test
      // for a Dockerfile to build the Docker image
      git ('https://github.com/jodichris17/flask-dockerized-jenkins')
      if (!fileExists("Dockerfile")) {
         error('Dockerfile missing.')
      }
   }
   stage('Build Docker') {
       // build the docker image from the source code using the BUILD_ID parameter in image name
         sh "docker build -t flask-app ."
   }
   stage("run docker container"){
        sh "docker run -p 8000:8000 --name flask-app -d flask-app "
    }
}
