pipeline {
    agent {label "slave-ci-cd"}

    stages {
            
        stage('Build') {
            // Creating env file 
            steps {
                    echo 'Building...'

                sh 'curl -sL https://deb.nodesource.com/setup_15.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'
                sh 'sudo apt-get install -y build-essential'
                sh 'sudo npm install'
                   
            }
        }
        
    }
   post {
            always {
                    echo 'Creating artifacts'
                    sh 'zip -r my_archive.zip /home/nirh237/workspace/CI'
                    echo 'archiving artifacts'
                    archiveArtifacts artifacts: 'my_archive.zip', onlyIfSuccessful: true
            }
    	}

}








