pipeline {
     agent any
	 tools {
	   maven 'Maven 3.0.5'
	 }
	 stages {
	    stage('maven version') {
		    steps {
			   sh 'mvn --version'
			}
		}
	    stage('Git Clone') {
		    steps{
			   git branch: 'main', changelog: false, credentialsId: '8b134f35-1b6c-4996-9e9e-3962acaccf5b', poll: false, url: 'https://github.com/pmnidhi/repo_july.git'
			}
	    }
	    stage('list content') {
	        steps {
	            sh 'ls -l'
	        }
	    }
		stage('maven clean') {
		    steps {
			   sh 'mvn clean'
			}
	    }
		stage('maven validate') {
		    steps {
			   sh 'mvn validate'
			}
	    }
		stage('maven test') {
		    steps {
			   sh 'mvn test'
			}
	    }
		stage('maven package') {
		    steps {
			   sh 'mvn package'
			}
	    }
		stage('maven deploy') {
		    steps {
			   sh 'mvn deploy'
			}
	    }
	}
}
