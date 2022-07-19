node {
    stage('git clone') {
       git branch: 'main', changelog: false, credentialsId: '85e4c59d-e692-404b-9827-8d4251656f10', poll: false, url: 'https://github.com/pmnidhi/repo.git'
    }
    stage('mvn clean') {
       sh 'mvn clean'
    }
	stage('sonar scan') {
        sh 'mvn sonar:sonar -Dsonar.projectKey=Project1 -Dsonar.host.url=http://54.92.200.27:9000 -Dsonar.login=93663165115dd671c54b372c8b1b554bedda4345'
    }
	stage('mvn validate') {
       sh 'mvn validate'
    }
	stage('mvn test ') {
       sh 'mvn test'
    }
	stage('mvn package') {
       sh 'mvn package'
    }
	
}

