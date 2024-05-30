pipeline {
	agent any

	stages {
		stage('Build') {
			agent {
				// need to install docker pipeline plugin to connect to docker daemon
				docker {
					image 'node:18-alpine'
					reuseNode true
				}
			}
			steps {
				sh '''
					echo "Start to compile Front-End..."
					node --version
					npm --version
					npm ci
					npm run build
				'''
			}
		}
	}
}