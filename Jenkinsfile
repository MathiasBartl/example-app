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
                    app.push("${env.BRANCH_NAME}-latest")
			app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
             }
      }
}
