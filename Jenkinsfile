pipeline {
    agent any
    stages {
        stage('Delete the workspace') {
            steps{
	        cleanWs()
            }
	}
	stage('Installing Java and Maven') {
	    steps {
		script{
			def maven_exists = fileExists '/usr/share/maven'
			if (maven_exists == true) {
			echo "Skipping maven install - already exists"
		}
		else {
	       	sh 'sudo apt-get  update -y && sudo apt-get upgrade -y'
		sh 'sudo apt install -y wget tree unzip openjdk-11-jdk maven'
      	    }

	}
	}
}
        stage("Download Java Code") {
	    steps{
		git credentialsId: 'git-repo-credentials', url: 'git@github.com:Anoop-kathait07/java-springboot-sample-app.git'
	       }
         	}
	
	stage("Compiling and Running Test Cases") {
		steps {
			sh 'mvn clean'
			sh 'mvn compile'
			sh 'mvn test'
		}
	}
	stage('Creating Package' ) {
	steps{
	     sh 'mvn package'

    }
}


