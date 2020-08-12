pipeline {
    agent any
    stages {
        stage('Scm'){
            steps {
                git 'https://github.com/Subhakaran057/game-of-life.git' 
            }
        }
        stage('Build'){
            steps {
                sh 'mvn package' 
            }
        }
        stage('Postbuild'){
            steps {
                junit 'gameoflife-web/target/surefire-reports/*.xml'
				archiveArtifacts artifacts: 'gameoflife-web/target/*.war'
            }
        }
    }
}
