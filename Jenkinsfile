pipeline {
    agent {
        kubernetes {
            label 'kaniko'
			//yamlFile 'kaniko.yaml'
			
        }
    }
    stages {
        stage('Build with Kaniko') {
		
            steps {
                script {
                    container(name: 'kaniko'){
                    def workspace = pwd()
                    //checkout scm
					echo "hello"
						sh 'cp $FILE config.json'
					sh 'ls -ltr'
					echo 'Execute test cases'
                    sh '/kaniko/executor --insecure --skip-tls-verify --context "' + workspace + '" --dockerfile "' + workspace + '/Dockerfile.kaniko"  --cleanup'
                    }
					
					}
				}
			}
        }		
}
