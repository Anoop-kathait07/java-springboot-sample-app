pipeline{
	agent any
	stages {
		stage('Delete the workspace') {
			steps{
				cleanWS()
			}
		}
	stage('Second Stage') {
		steps {
			echo "Second stage"
		}
	}
      stage('Third Stage') {
	steps{
		echo "Third stage"
		}
	}
	
	}
}
