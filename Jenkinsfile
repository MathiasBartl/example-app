node {
      def app
      stage('Clone Repository'){
            checkout scm
      }
      stage('Build Image'){
             app = docker.build('mjuuso/example-app')
      }
      stage('Push Image'){
             docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials'){
                    app.push('latest')
             }
      }
}