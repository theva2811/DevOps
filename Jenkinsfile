pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('jenkins-test')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t theva2811/node-pipelineproject:latest.'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push theva2811/node-pipelineproject:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}

