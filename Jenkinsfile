pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('theva2811')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t dev .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u theva2811 --dckr_pat_P3p0J1BNM2fql8yraE-G1TZGwJc-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push dev theva2811/node-pipelineproject:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}

